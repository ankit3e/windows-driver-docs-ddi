---
UID: NF:ringcollection.NetRingCollectionGetFragmentRing
title: NetRingCollectionGetFragmentRing function (ringcollection.h)
description: The NetRingCollectionGetFragmentRing gets the fragment ring for a packet queue.
tech.root: netvista
ms.date: 02/06/2019
keywords: ["NetRingCollectionGetFragmentRing function"]
ms.keywords: NetRingCollectionGetFragmentRing
req.header: ringcollection.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.29
req.umdf-ver: 2.33 
req.lib: 
req.dll: 
req.irql: Any level as long as target memory is resident
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.alt-api: 
req.alt-loc: 
targetos: Windows
f1_keywords:
 - NetRingCollectionGetFragmentRing
 - ringcollection/NetRingCollectionGetFragmentRing
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ringcollection.h
api_name:
 - NetRingCollectionGetFragmentRing
---

# NetRingCollectionGetFragmentRing function


## -description

The **NetRingCollectionGetFragmentRing** gets the fragment ring for a packet queue.

## -parameters

### -param Rings

A pointer to a [**NET_RING_COLLECTION**](../ringcollection/ns-ringcollection-_net_ring_collection.md) structure that describes this packet queue's net rings.

## -returns

Returns a pointer to the fragment [**NET_RING**](../ring/ns-ring-_net_ring.md) for the packet queue.

## -remarks

Client drivers typically call this function when they need to work with a fragment ring directly, such as when the driver is posting information to hardware. For example, during transmit a driver might use the fragment ring's **ElementIndexMask** to retrieve the correct fragment that is being posted to hardware in order to populate the hardware descriptor. 

For examples of using this function, see the [Realtek sample driver](https://github.com/Microsoft/NetAdapter-Cx-Driver-Samples/tree/release_1809/RtEthSample).

## -see-also

[Introduction to net rings](/windows-hardware/drivers/netcx/introduction-to-net-rings)
