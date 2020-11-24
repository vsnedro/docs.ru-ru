---
title: Метод ICorDebugType::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
ms.openlocfilehash: 1cb9729f175a2e82e88386b0694467c6fe05636a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684464"
---
# <a name="icordebugtypegetclass-method"></a>Метод ICorDebugType::GetClass

Возвращает указатель интерфейса на объект ICorDebugClass, представляющий универсальный тип, экземпляр которого не был создан.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppClass`  
 заполняет Указатель на адрес `ICorDebugClass` интерфейса, представляющий универсальный тип, экземпляр которого не был создан.  
  
## <a name="remarks"></a>Комментарии  

 `GetClass` может вызываться только при определенных условиях. Вызовите метод [ICorDebugType:: GetType](icordebugtype-gettype-method.md) перед вызовом метода `GetClass` . Если `ICorDebugType::GetType` возвращает значение корелементтипе, которое равно ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, `GetClass` можно вызвать метод, чтобы получить неэкземплярный тип для универсального типа.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
