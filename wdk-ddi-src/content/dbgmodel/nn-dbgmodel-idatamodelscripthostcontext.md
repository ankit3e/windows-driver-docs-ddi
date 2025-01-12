---
UID: NN:dbgmodel.IDataModelScriptHostContext
title: IDataModelScriptHostContext (dbgmodel.h)
description: Implemented by the underlying host debugger, represents information about where the debug host is bridging the script.
ms.date: 10/05/2018
keywords: ["IDataModelScriptHostContext interface"]
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDataModelScriptHostContext
 - dbgmodel/IDataModelScriptHostContext
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptHostContext
---

# IDataModelScriptHostContext interface


## -description

Implemented by the underlying host debugger, represents information about where the debug host is bridging the script.

## -inheritance

IDataModelScriptHostContext inherits from IUnknown.

## -remarks

A host interface which is used by the script provider as a container for the contents of the script. How the contents of a script surface other than the manipulations that it performs to the object model of the debugger application is up to the particular debug host. This interface allows the script provider to get information about where to place its contents. See [Data Model C++ Scripting Interfaces](/windows-hardware/drivers/debugger/data-model-cpp-scripting) for more information.

The [IDebugHostScriptHost](nn-dbgmodel-idebughostscripthost.md) interface is the interface used by a script provider to get a context from the debug host for a newly created script. This context includes an object (provided by the debug host) where the script provider can place any bridges between the data model and the scripting environment. Such bridges might, for instance, be data model methods which invoke script functions. Doing this allows a caller on the data model side to invoke script methods by utilization of the Call method on [IModelMethod](nn-dbgmodel-imodelmethod.md) interface.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
