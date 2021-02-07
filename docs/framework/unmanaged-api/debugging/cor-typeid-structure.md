---
description: 'Дополнительные сведения: структура COR_TYPEID'
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
ms.openlocfilehash: fe246d544697275ffc4ea3ab6ed21c0f33863881
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712218"
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
  
## <a name="remarks"></a>Remarks  

 `COR_TYPEID`Структура возвращается несколькими методами отладки, которые предоставляют сведения об объектах, которые должны быть собраны в мусор. Затем его можно передать в качестве аргумента другим методам отладки, которые предоставляют дополнительные сведения об этом элементе. Например, при перечислении объекта [икордебугхеапенум](icordebugheapenum-interface.md) можно получить отдельные объекты [COR_HEAPOBJECT](cor-heapobject-structure.md) , представляющие отдельные объекты в управляемой куче. Затем можно передать `COR_TYPEID` значение из `COR_HEAPOBJECT.type` поля в метод [метод ICorDebugProcess5:: жеттипефортипеид](icordebugprocess5-gettypefortypeid-method.md) , чтобы получить объект ICorDebugType, предоставляющий сведения о типе объекта.  
  
 `COR_TYPEID`Объект должен быть непрозрачным. Доступ к отдельным полям не должен осуществляться или манипулировать им. Его единственное использование — это идентификатор, предоставляемый как `out` параметр в вызове метода, который, в свою очередь, может быть передан другим методам для предоставления дополнительных сведений.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
