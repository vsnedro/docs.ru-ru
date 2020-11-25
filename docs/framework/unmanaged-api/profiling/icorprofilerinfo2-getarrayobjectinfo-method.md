---
title: Метод ICorProfilerInfo2::GetArrayObjectInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetArrayObjectInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type:
- apiref
ms.openlocfilehash: a1e321e141059ccf1da7292d28e7099418a5134e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727202"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a>Метод ICorProfilerInfo2::GetArrayObjectInfo

Возвращает подробные сведения об объекте массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a>Параметры  

 `objectId`  
 окне Идентификатор допустимого объекта массива.  
  
 `cDimensions`  
 окне Ранг (число измерений) массива.  
  
 `pDimensionSizes`  
 заполняет Массив, содержащий целые числа, каждый из которых представляет размер измерения массива.  
  
 `pDimensionLowerBounds`  
 заполняет Массив, содержащий целые числа, каждый из которых представляет нижнюю границу измерения массива.  
  
 `ppData`  
 заполняет Указатель на адрес необработанного буфера для массива, который располагается в соответствии с соглашением C++.  
  
## <a name="remarks"></a>Комментарии  

 `pDimensionSizes`И `pDimensionLowerBounds` — это параллельные массивы, поэтому элементы, расположенные по одному индексу в каждом массиве, являются характеристиками одной и той же сущности.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
