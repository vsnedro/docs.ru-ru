---
description: 'Дополнительные сведения о методе: ICorDebugManagedCallback:: LoadAssembly'
title: Метод ICorDebugManagedCallback::LoadAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadAssembly
helpviewer_keywords:
- LoadAssembly method [.NET Framework debugging]
- ICorDebugManagedCallback::LoadAssembly method [.NET Framework debugging]
ms.assetid: 55cb673a-e240-43a6-a406-6912e7c0fe66
topic_type:
- apiref
ms.openlocfilehash: b90391f3c6286323db11dadae841db38f9b785a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722806"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a>Метод ICorDebugManagedCallback::LoadAssembly

Уведомляет отладчик о том, что сборка среды CLR была успешно загружена.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAppDomain`  
 окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в который была загружена сборка.  
  
 `pAssembly`  
 окне Указатель на объект ICorDebugAssembly, представляющий сборку.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод UnloadAssembly](icordebugmanagedcallback-unloadassembly-method.md)
- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
