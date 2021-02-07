---
description: 'Дополнительные сведения о методе: ICorDebugType2:: TypeID'
title: 'Метод ICorDebugType2:: TypeID'
ms.date: 03/30/2017
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
ms.openlocfilehash: 8143ede1a11ee5f73c49fc723920f53430339ed0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738108"
---
# <a name="icordebugtype2gettypeid-method"></a>Метод ICorDebugType2:: TypeID

Возвращает [COR_TYPEID](cor-typeid-structure.md) для этого типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `id`  
 заполняет Указатель на [COR_TYPEID](cor-typeid-structure.md) для этого элемента ICorDebugType.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое. В `HRESULT` число этих кодов входят следующие.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|`S_OK`|Метод успешно выполнен. Метод получил допустимый [COR_TYPEID](cor-typeid-structure.md).|  
|`CORDBG_E_CLASS_NOT_LOADED`|Тип не был загружен.|  
|`CORDBG_E_UNSUPPORTED`|Этот тип не поддерживается.|  
  
## <a name="remarks"></a>Remarks  

 Этот метод предоставляет сопоставление из объекта ICorDebugType, представляющего тип, который может быть или не загружен в среду выполнения, в [COR_TYPEID](cor-typeid-structure.md), который служит в качестве непрозрачного маркера, определяющего тип, загруженный в среду выполнения.  
  
 Если тип, который представляет объект ICorDebugType, еще не загружен, этот метод возвращает `CORDBG_E_CLASS_NOT_LOADED` .  Если тип не поддерживается, он возвращает `CORDBG_E_UNSUPPORTED` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugType2](icordebugtype2-interface.md)
