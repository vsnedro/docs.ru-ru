---
title: Структура COR_TYPEID
ms.date: 03/30/2017
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
ms.openlocfilehash: 5eeb5aef7edaa23385190a309144e1477da741e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697445"
---
# <a name="cor_typeid-structure"></a>Структура COR_TYPEID

Содержит идентификатор типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`token1`|Первый токен.|  
|`token2`|Второй токен.|  
  
## <a name="remarks"></a>Комментарии  

 `COR_TYPEID`Структура возвращается несколькими методами отладки, которые предоставляют сведения об объектах, которые должны быть собраны в мусор. Затем его можно передать в качестве аргумента другим методам отладки, которые предоставляют дополнительные сведения об этом элементе. Например, при перечислении объекта [икордебугхеапенум](icordebugheapenum-interface.md) можно получить отдельные объекты [COR_HEAPOBJECT](cor-heapobject-structure.md) , представляющие отдельные объекты в управляемой куче. Затем можно передать `COR_TYPEID` значение из `COR_HEAPOBJECT.type` поля в метод [метод ICorDebugProcess5:: жеттипефортипеид](icordebugprocess5-gettypefortypeid-method.md) , чтобы получить объект ICorDebugType, предоставляющий сведения о типе объекта.  
  
 `COR_TYPEID`Объект должен быть непрозрачным. Доступ к отдельным полям не должен осуществляться или манипулировать им. Его единственное использование — это идентификатор, предоставляемый как `out` параметр в вызове метода, который, в свою очередь, может быть передан другим методам для предоставления дополнительных сведений.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
