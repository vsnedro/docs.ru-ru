---
title: Интерфейс ICorDebugArrayValue
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue interface
helpviewer_keywords:
- ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type:
- apiref
ms.openlocfilehash: bd1e86b83c43af20604416f158ab9e74f399821b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894971"
---
# <a name="icordebugarrayvalue-interface"></a>Интерфейс ICorDebugArrayValue

Подкласс ICorDebugHeapValue, представляющий одномерный или многомерный массив.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetBaseIndicies](icordebugarrayvalue-getbaseindicies-method.md)|Возвращает базовый индекс каждого измерения в массиве.|  
|[Метод GetCount](icordebugarrayvalue-getcount-method.md)|Возвращает общее число элементов в массиве.|  
|[Метод GetDimensions](icordebugarrayvalue-getdimensions-method.md)|Возвращает размеры массива.|  
|[Метод GetElement](icordebugarrayvalue-getelement-method.md)|Возвращает значение, представляющее заданный элемент в массиве.|  
|[Метод GetElementAtPosition](icordebugarrayvalue-getelementatposition-method.md)|Возвращает элемент в заданной позиции, рассматривая массив как одномерный массив с отсчетом от нуля.|  
|[Метод GetElementType](icordebugarrayvalue-getelementtype-method.md)|Возвращает простой тип элементов в массиве.|  
|[Метод GetRank](icordebugarrayvalue-getrank-method.md)|Получает число измерений в массиве.|  
|[Метод HasBaseIndicies](icordebugarrayvalue-hasbaseindicies-method.md)|Определяет, имеет ли массив базовые индексы.|  
  
## <a name="remarks"></a>Remarks  
 `ICorDebugArrayValue`поддерживает одномерный и многомерный массивы.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
