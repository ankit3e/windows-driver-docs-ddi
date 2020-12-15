---
UID: NF:ndis.NET_BUFFER_CHECKSUM_BIAS
title: NET_BUFFER_CHECKSUM_BIAS macro (ndis.h)
description: NET_BUFFER_CHECKSUM_BIAS is a macro that NDIS drivers use to get the ChecksumBias member of a NET_BUFFER structure.
tech.root: netvista
ms.date: 04/12/2018
keywords: ["NET_BUFFER_CHECKSUM_BIAS macro"]
ms.keywords: NET_BUFFER_CHECKSUM_BIAS
req.header: ndis.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
f1_keywords:
 - NET_BUFFER_CHECKSUM_BIAS
 - ndis/NET_BUFFER_CHECKSUM_BIAS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NET_BUFFER_CHECKSUM_BIAS
---

# NET_BUFFER_CHECKSUM_BIAS macro


## -description

**NET_BUFFER_CHECKSUM_BIAS** is a macro that NDIS drivers use to get the **ChecksumBias** member of a [**NET_BUFFER**](ns-ndis-_net_buffer.md) structure.

## -parameters

### -param _NB

A pointer to a **NET_BUFFER** structure.

## -returns

**NET_BUFFER_CHECKSUM_BIAS** returns the value of the **ChecksumBias** member of the indicated **NET_BUFFER** structure.

## -remarks

The return value specifies the number of bytes of data to skip over at the beginning of the data buffer when computing a checksum. This value is used by the TCP/IP protocol.

## -see-also

[**NET_BUFFER**](ns-ndis-_net_buffer.md)
