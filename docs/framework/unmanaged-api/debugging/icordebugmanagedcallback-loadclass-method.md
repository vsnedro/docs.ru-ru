---
description: 'Дополнительные сведения о методе: ICorDebugManagedCallback:: LoadClass'
title: Метод ICorDebugManagedCallback::LoadClass
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
ms.openlocfilehash: 6f670a2f0798c7edfdc4292334cf9534e59a3007
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660613"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a>Метод ICorDebugManagedCallback::LoadClass

Уведомляет отладчик о том, что класс был загружен.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAppDomain`  
 окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в который был загружен класс.  
  
 `c`  
 окне Указатель на объект ICorDebugClass, представляющий класс.  
  
## <a name="remarks"></a>Remarks  

 Этот обратный вызов происходит, только если для модуля, содержащего класс, была включена загрузка класса. Загрузка класса всегда включена для динамических модулей.  
  
 `LoadClass`Обратный вызов предоставляет соответствующее время для привязки точек останова к вновь созданным классам в динамических модулях.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод UnloadClass](icordebugmanagedcallback-unloadclass-method.md)
- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
