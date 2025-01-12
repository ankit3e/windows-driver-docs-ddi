---
UID: NF:fwpmk.FwpmCalloutCreateEnumHandle0
tech.root: netvista
title: FwpmCalloutCreateEnumHandle0
ms.date: 05/31/2024
targetos: Windows
description: The FwpmCalloutCreateEnumHandle0 function creates a handle used to enumerate a set of callout objects.
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
 - FwpmCalloutCreateEnumHandle0
f1_keywords:
 - FwpmCalloutCreateEnumHandle0
 - fwpmk/FwpmCalloutCreateEnumHandle0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmCalloutCreateEnumHandle0
---

## -description

The **FwpmCalloutCreateEnumHandle0** function creates a handle used to enumerate a set of callout objects.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param enumTemplate [in, optional]

Template to selectively restrict the enumeration.

### -param enumHandle [out]

Handle of the newly created enumeration.

## -returns

| Return code/value | Description |
| --- | --- |
| **ERROR_SUCCESS**<br>0 | The enumerator was created successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/desktop/FWP/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

If *enumTemplate* is **NULL**, all callout objects are returned.

The enumerator is not live, meaning it does not reflect changes made to the system after the call to **FwpmCalloutCreateEnumHandle0** returns. If you need to ensure that the results are current, you must call **FwpmCalloutCreateEnumHandle0** and **[FwpmCalloutEnum0](nf-fwpmk-fwpmcalloutenum0.md)** from within the same explicit transaction.

The caller must call **[FwpmCalloutDestroyEnumHandle0](nf-fwpmk-fwpmcalloutdestroyenumhandle0.md)** to free the returned handle.

The caller needs **[FWPM_ACTRL_ENUM](/windows/desktop/FWP/access-right-identifiers)** access to the callouts' containers and **FWPM_ACTRL_READ** access to the callouts. Only callouts to which the caller has **FWPM_ACTRL_READ** access will be returned. See [Access Control](/windows/desktop/FWP/access-control) for more information.

**FwpmCalloutCreateEnumHandle0** is a specific implementation of FwpmCalloutCreateEnumHandle. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[FwpmCalloutEnum0](nf-fwpmk-fwpmcalloutenum0.md)**
- **[FwpmCalloutDestroyEnumHandle0](nf-fwpmk-fwpmcalloutdestroyenumhandle0.md)**
- **[FWPM_ACTRL_ENUM](/windows/desktop/FWP/access-right-identifiers)**
- **[FWPM_CALLOUT_ENUM_TEMPLATE0](/windows/win32/api/fwpmtypes/ns-fwpmtypes-fwpm_callout_enum_template0)**
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
