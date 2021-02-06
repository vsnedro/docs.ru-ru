---
description: 'Дополнительные сведения о методе: метод ICorDebugProcess5:: Жеттипефиелдс'
title: Метод ICorDebugProcess5::GetTypeFields
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
ms.openlocfilehash: bdbb0be76400262d83876b9fc37cc4f00eb34e43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649823"
---
# <a name="icordebugprocess5gettypefields-method"></a>Метод ICorDebugProcess5::GetTypeFields

Предоставляет сведения о полях, принадлежащих типу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `id`  
 окне Идентификатор типа, сведения о поле которого извлекаются.  
  
 `celt`  
 окне Число объектов [COR_FIELD](cor-field-structure.md) , сведения о полях которых нужно получить.  
  
 `fields`  
 заполняет Массив объектов [COR_FIELD](cor-field-structure.md) , которые предоставляют сведения о полях, принадлежащих типу.  
  
 `pceltNeeded`  
 заполняет Указатель на число объектов [COR_FIELD](cor-field-structure.md) , включаемых в `fields` .  
  
## <a name="remarks"></a>Remarks  

 `celt`Параметр, указывающий количество полей, сведения о полях которых использует метод для заполнения `fields` , должно соответствовать значению `COR_TYPE_LAYOUT::numFields` поля.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
