---
UID: NF:fwpmk.FwpmConnectionCreateEnumHandle0
tech.root: netvista
title: FwpmConnectionCreateEnumHandle0
ms.date: 06/04/2024
targetos: Windows
description: The FwpmConnectionCreateEnumHandle0 function creates a handle used to enumerate a set of connection objects.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: fwpmk.h
req.idl: 
req.include-header: 
req.irql: <= PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: fwpkclnt.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fwpmk.h
api_name:
 - FwpmConnectionCreateEnumHandle0
f1_keywords:
 - FwpmConnectionCreateEnumHandle0
 - fwpmk/FwpmConnectionCreateEnumHandle0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmConnectionCreateEnumHandle0
---

## -description

The **FwpmConnectionCreateEnumHandle0** function creates a handle used to enumerate a set of connection objects.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param enumTemplate [in, optional]

Template for selectively restricting the enumeration.

### -param enumHandle [out]

Address of a **HANDLE** variable. On function return, it contains the handle for the enumeration.

## -returns

| Return code/value | Description |
| --- | --- |
| **ERROR_SUCCESS**<br>0 | The enumerator was created successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

If *enumTemplate* is **NULL**, all connection objects are returned.

The caller must free the returned handle by a call to **[FwpmConnectionDestroyEnumHandle0](nf-fwpmk-fwpmconnectiondestroyenumhandle0.md)**.

The caller needs [FWPM_ACTRL_ENUM](/windows/desktop/FWP/access-right-identifiers) access to the connection objects' containers and **FWPM_ACTRL_READ** access to the connection objects. See [Access Control](/windows/desktop/FWP/access-control) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[FwpmConnectionDestroyEnumHandle0](nf-fwpmk-fwpmconnectiondestroyenumhandle0.md)**
- **[FWPM_CONNECTION_ENUM_TEMPLATE0](/windows/desktop/api/fwpmtypes/ns-fwpmtypes-fwpm_connection_enum_template0)**
- [FWPM_ACTRL_ENUM](/windows/desktop/FWP/access-right-identifiers)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [Access Control](/windows/desktop/FWP/access-control)
