---
title: Метод ICorDebugModule::EnableClassLoadCallbacks
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableClassLoadCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type:
- apiref
ms.openlocfilehash: 1f6c6ae3b7cb45b049d0fb0d88bbf89121bccfd7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710419"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a>Метод ICorDebugModule::EnableClassLoadCallbacks

Определяет, вызываются ли для этого модуля обратные вызовы [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback:: унлоадкласс](icordebugmanagedcallback-unloadclass-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `bClassLoadCallbacks`  
 окне Задайте это значение `true` , чтобы среда CLR вызывала `ICorDebugManagedCallback::LoadClass` `ICorDebugManagedCallback::UnloadClass` методы и при возникновении связанных с ними событий.  
  
 Значение по умолчанию — `false` для модулей, не являющихся динамическими. Значение всегда используется `true` для динамических модулей и не может быть изменено.  
  
## <a name="remarks"></a>Комментарии  

 `ICorDebugManagedCallback::LoadClass` `ICorDebugManagedCallback::UnloadClass` Обратные вызовы и всегда включены для динамических модулей и не могут быть отключены.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел
