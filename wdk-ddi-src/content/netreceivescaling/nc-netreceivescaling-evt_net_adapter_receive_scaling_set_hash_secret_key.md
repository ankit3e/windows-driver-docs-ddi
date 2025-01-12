---
UID: NC:netreceivescaling.EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY
title: EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY (netreceivescaling.h)
description: The EvtNetAdapterReceiveScalingSetHashSecretKey callback function is implemented by the client driver to set the hash secret key for the network interface controller (NIC).
tech.root: netvista
ms.date: 04/01/2022
keywords: ["EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY callback function"]
req.header: netreceivescaling.h
req.include-header: netadaptercx.h 
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.25
req.umdf-ver: 2.33 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY
 - netreceivescaling/EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - netreceivescaling.h
api_name:
 - EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY
---

# EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY callback function


## -description

The *EvtNetAdapterReceiveScalingSetHashSecretKey* callback function is implemented by the client driver to set the hash secret key for the network interface controller (NIC).

## -parameters

### -param Adapter [_In_]

The NETADAPTER object the client driver obtained in a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param HashSecretKey [_In_]

A pointer to a [NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY](ns-netreceivescaling-_net_adapter_receive_scaling_hash_secret_key.md) structure that contains the hash secret key for validating hash calculations.

## -returns

Returns STATUS_SUCCESS if the hash secret key was set successfully. Otherwise, returns an appropriate NTSTATUS error code.

## -prototype

```cpp
//Declaration

EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY EvtNetAdapterReceiveScalingSetHashSecretKey; 

// Definition

NTSTATUS EvtNetAdapterReceiveScalingSetHashSecretKey 
(
	_In_	NETADAPTER 											Adapter,
	_In_	const NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY *	HashSecretKey
)
{...}

typedef EVT_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY *PFN_NET_ADAPTER_RECEIVE_SCALING_SET_HASH_SECRET_KEY;
```

## -remarks

Register your implementation of this callback function by setting the appropriate member of the [NET_ADAPTER_RECEIVE_SCALING_CAPABILITIES](ns-netreceivescaling-_net_adapter_receive_scaling_capabilities.md) structure and then calling [NetAdapterSetReceiveScalingCapabilities](nf-netreceivescaling-netadaptersetreceivescalingcapabilities.md). Client drivers typically call **NetAdapterSetReceiveScalingCapabilities** when starting a net adapter, before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).



### Example

In this callback, NIC client drivers program the supplied hash secret key to their hardware for use in verifying RSS hash calculations.

```C++
NTSTATUS
MyEvtNetAdapterReceiveScalingSetHashSecretKey(
	_In_	NETADAPTER 											Adapter,
	_In_	const NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY *	HashSecretKey	
)
{
	const UINT32* key = (const UINT32*)HashSecretKey->Key;
	if(!MyHardwareRssSetHashSecretKey)
	{
		WdfDeviceSetFailed(Adapter->WdfDevice, WdfDeviceFailedAttemptRestart);
		return STATUS_UNSUCCESSFUL;
	}

	return STATUS_SUCCESS;
}
```

## -see-also

[NET_ADAPTER_RECEIVE_SCALING_HASH_SECRET_KEY](ns-netreceivescaling-_net_adapter_receive_scaling_hash_secret_key.md)

[NetAdapterCx Receive Side Scaling](/windows-hardware/drivers/netcx/netadaptercx-receive-side-scaling-rss-)
