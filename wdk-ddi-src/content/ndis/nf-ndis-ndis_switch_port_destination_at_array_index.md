---
UID: NF:ndis.NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX
title: NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX macro (ndis.h)
description: Hyper-V extensible switch extensions use the NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX macro to access an NDIS_SWITCH_PORT_DESTINATION element inside an NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY structure.
tech.root: netvista
ms.date: 04/17/2018
keywords: ["NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX macro"]
ms.keywords: NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX
req.header: ndis.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
returns-override: true
f1_keywords:
 - NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX
 - ndis/NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX
---

# NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX macro


## -description

Hyper-V extensible switch extensions use the **NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX** macro to access an [**NDIS_SWITCH_PORT_DESTINATION**](ns-ndis-_ndis_switch_port_destination.md) element inside an [**NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY**](ns-ndis-_ndis_switch_forwarding_destination_array.md) structure.

## -parameters

### -param _DestArray_

A pointer to an **NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY** structure.

### -param _Index_

A USHORT value that specifies the zero-based index of the **NDIS_SWITCH_PORT_DESTINATION** element inside the **NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY**.

> [!NOTE]
> This value must be less than the value of the **NumElements** member of the **NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY** structure.

## -returns

The **NDIS_SWITCH_PORT_DESTINATION_AT_ARRAY_INDEX** macro returns a pointer to the specified [**NDIS_SWITCH_PORT_DESTINATION**](ns-ndis-_ndis_switch_port_destination.md) element inside the [**NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY**](ns-ndis-_ndis_switch_forwarding_destination_array.md).

## -remarks

## -see-also

[**NDIS_SWITCH_PORT_DESTINATION**](ns-ndis-_ndis_switch_port_destination.md)

[**NDIS_SWITCH_FORWARDING_DESTINATION_ARRAY**](ns-ndis-_ndis_switch_forwarding_destination_array.md)

