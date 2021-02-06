---
description: 'Дополнительные сведения о методе: метод ICorDebugProcess5:: Енумератехеапрегионс'
title: Метод ICorDebugProcess5::EnumerateHeapRegions
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeapRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type:
- apiref
ms.openlocfilehash: 034b1ebcd003e6854fa4f308b0464aac0a8c4839
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649849"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a>Метод ICorDebugProcess5::EnumerateHeapRegions

Возвращает перечислитель для диапазонов памяти управляемой кучи.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppRegions`  
 заполняет Указатель на адрес объекта интерфейса [икордебугхеапсегментенум](icordebugheapsegmentenum-interface.md) , который является перечислителем для диапазонов памяти, в которых объекты находятся в управляемой куче.  
  
## <a name="remarks"></a>Remarks  

 Перед вызовом `ICorDebugProcess5::EnumerateHeapRegions` метода необходимо вызвать метод [метод ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) и проверить значение `areGCStructuresValid` поля возвращенного [COR_HEAPINFO](cor-heapinfo-structure.md) объекта, чтобы гарантировать, что куча сборки мусора в ее текущем состоянии является перечислимым. Кроме `ICorDebugProcess5::EnumerateHeapRegions` того, метод возвращает, `E_FAIL` Если вы присоединяетесь слишком рано в течение времени существования процесса до создания областей памяти.  
  
 Этот метод гарантирует перечисление всех областей памяти, которые могут содержать управляемые объекты, но не гарантирует, что управляемые объекты фактически находятся в этих регионах. Объект коллекции [икордебугхеапсегментенум](icordebugheapsegmentenum-interface.md) может включать в себя пустые или зарезервированные регионы памяти.  
  
 Объект интерфейса [икордебугхеапсегментенум](icordebugheapsegmentenum-interface.md) является стандартным перечислителем, производным от интерфейса ICorDebugEnum, который позволяет перечислить [COR_SEGMENTные](cor-segment-structure.md) объекты. Каждый объект [COR_SEGMENT](cor-segment-structure.md) предоставляет сведения о диапазоне памяти определенного сегмента вместе с поколением объектов в этом сегменте.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
