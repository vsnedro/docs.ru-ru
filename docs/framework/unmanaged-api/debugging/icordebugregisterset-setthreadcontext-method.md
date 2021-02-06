---
description: 'Дополнительные сведения о методе: ICorDebugRegisterSet:: SetThreadContext'
title: Метод ICorDebugRegisterSet::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type:
- apiref
ms.openlocfilehash: 8d874b1864e85e477260632ad6012dbbf10aefb2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637694"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a>Метод ICorDebugRegisterSet::SetThreadContext

`SetThreadContext` не реализован в платформа .NET Framework версии 2,0. Этот метод не следует вызывать.  
  
> [!NOTE]
> Используйте операцию более высокого уровня [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) , чтобы задать контекст потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:** 1,1, 1,0  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)
- [Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
