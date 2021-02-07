---
description: 'Дополнительные сведения о методе: метод ICorDebugProcess5:: Жеттипефортипеид'
title: Метод ICorDebugProcess5::GetTypeForTypeID
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeForTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type:
- apiref
ms.openlocfilehash: a18543b0afc867dc3796264ac1d08a775c73ca59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746377"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a>Метод ICorDebugProcess5::GetTypeForTypeID

Преобразует идентификатор типа в значение ICorDebugType.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `id`  
 окне Идентификатор типа.  
  
 `ppType`  
 заполняет Указатель на адрес объекта ICorDebugType.  
  
## <a name="remarks"></a>Remarks  

 В некоторых случаях методы, возвращающие идентификатор типа, могут возвращать `COR_TYPEID` значение null. Если это значение передается в качестве `id` аргумента, `GetTypeForTypeID` метод завершится ошибкой и вернет значение `E_FAIL` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
