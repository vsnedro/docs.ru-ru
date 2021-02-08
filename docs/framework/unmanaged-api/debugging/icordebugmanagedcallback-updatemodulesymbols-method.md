---
description: 'Дополнительные сведения о методе: ICorDebugManagedCallback:: UpdateModuleSymbols'
title: Метод ICorDebugManagedCallback::UpdateModuleSymbols
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UpdateModuleSymbols
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type:
- apiref
ms.openlocfilehash: 1e20ee50cdbe0b36d0677051f1fe2b1c777e6cd6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790936"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a>Метод ICorDebugManagedCallback::UpdateModuleSymbols

Уведомляет отладчик о том, что символы для модуля среды CLR были изменены.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAppDomain`  
 окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий модуль, в котором были изменены символы.  
  
 `pModule`  
 окне Указатель на объект ICorDebugModule, представляющий модуль, в котором были изменены символы.  
  
 `pSymbolStream`  
 окне Указатель на COM-объект Win32 `IStream` , содержащий измененные символы.  
  
## <a name="remarks"></a>Remarks  

 Этот метод предоставляет возможность обновить представление символов модуля отладчика путем вызова [ISymUnmanagedReader:: UpdateSymbolStore](../diagnostics/isymunmanagedreader-updatesymbolstore-method.md) или [ISymUnmanagedReader:: ReplaceSymbolStore](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md).  
  
 Этот обратный вызов может происходить несколько раз для одного модуля.  
  
 Отладчик должен попытаться привязать несвязанные точки останова на уровне источника.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
