---
UID: NF:fwpmk.IPsecDospSetSecurityInfo0
tech.root: netvista
title: IPsecDospSetSecurityInfo0
ms.date: 06/19/2024
targetos: Windows
description: The IPsecDospSetSecurityInfo0 function sets specified security information in the security descriptor of the IPsec DoS Protection database.
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
 - IPsecDospSetSecurityInfo0
f1_keywords:
 - IPsecDospSetSecurityInfo0
 - fwpmk/IPsecDospSetSecurityInfo0
dev_langs:
 - c++
helpviewer_keywords:
 - IPsecDospSetSecurityInfo0
---

## -description

The **IPsecDospSetSecurityInfo0** function sets specified security information in the security descriptor of the IPsec DoS Protection database.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param securityInfo [in]

The type of security information to set.

### -param sidOwner [in, optional]

The owner's security identifier (SID) to be set in the security descriptor.

### -param sidGroup [in, optional]

The group's SID to be set in the security descriptor.

### -param dacl [in, optional]

The discretionary access control list (DACL) to be set in the security descriptor.

### -param sacl [in, optional]

The system access control list (SACL) to be set in the security descriptor.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The security information was set successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

This function behaves like the standard Win32 **[SetSecurityInfo](/windows/desktop/api/aclapi/nf-aclapi-setsecurityinfo)** function. The caller needs the same standard access rights as described in the **SetSecurityInfo** reference topic.

**IPsecDospSetSecurityInfo0** is a specific implementation of **IPsecDospSetSecurityInfo**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[IPsecDospGetSecurityInfo0](nf-fwpmk-ipsecdospgetsecurityinfo0.md)**
- **[SetSecurityInfo](/windows/desktop/api/aclapi/nf-aclapi-setsecurityinfo)**
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
