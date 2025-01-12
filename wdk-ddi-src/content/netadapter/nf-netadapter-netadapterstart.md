---
UID: NF:netadapter.NetAdapterStart
title: NetAdapterStart function (netadapter.h)
description: The NetAdapterStart function starts a NETADAPTER object.
tech.root: netvista
ms.date: 03/30/2022
keywords: ["NetAdapterStart function"]
ms.keywords: NetAdapterStart
req.header: netadapter.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.25
req.umdf-ver: 2.33 
req.lib: netadaptercxstub.lib
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
 - NetAdapterStart
 - netadapter/NetAdapterStart
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetAdapterStart
---

# NetAdapterStart function


## -description

The **NetAdapterStart** function starts a NETADAPTER object.

## -parameters

### -param Adapter [_In_]

The **NETADAPTER** object created by a prior call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

## -returns

The function returns STATUS_SUCCESS if the operation succeeds. Otherwise, this function may return an appropriate NTSTATUS error code.

## -remarks

For this function to succeed, the **NETADAPTER** object must have been previously created by calling [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

## -see-also

[**NetAdapterCreate**](nf-netadapter-netadaptercreate.md)

[**NetAdapterStop**](nf-netadapter-netadapterstop.md)

