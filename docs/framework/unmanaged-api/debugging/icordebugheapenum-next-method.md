---
title: Метод ICorDebugHeapEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
ms.openlocfilehash: 320b3ca55a60ec7751c88a246ab6ee90b6b6c4cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724355"
---
# <a name="icordebugheapenumnext-method"></a>Метод ICorDebugHeapEnum::Next

Возвращает указанное число экземпляров [COR_HEAPOBJECT](cor-heapobject-structure.md) , содержащих сведения об объектах в управляемой куче.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Параметры  

 celt  
 [in] Количество объектов, которые должны быть получены.  
  
 объекты  
 заполняет Массив указателей, каждый из которых указывает на объект [COR_HEAPOBJECT](cor-heapobject-structure.md) , предоставляющий сведения об объекте в управляемой куче.  
  
 pceltFetched  
 заполняет Указатель на число объектов [COR_HEAPOBJECT](cor-heapobject-structure.md) , фактически возвращаемых в `objects` . Это значение может быть `null`, если параметр `celt` имеет значение 1.  
  
## <a name="remarks"></a>Комментарии  

 Поле `COR_HEAPOBJECT.type` является идентификатором вложенного COM-интерфейса с подсчетом ссылок. Эта ссылка должна быть выпущена вызывающим объектом `ICorDebugHeapEnum::Next`.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugHeapEnum](icordebugheapenum-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
