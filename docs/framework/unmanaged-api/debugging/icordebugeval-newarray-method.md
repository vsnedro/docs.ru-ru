---
description: 'Дополнительные сведения о методе: ICorDebugEval:: NewArray'
title: Метод ICorDebugEval::NewArray
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
ms.openlocfilehash: 1344a99450974369533b1c54b641c036fc64e3ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693984"
---
# <a name="icordebugevalnewarray-method"></a>Метод ICorDebugEval::NewArray

Выделяет новый массив указанного типа элемента и измерений.  
  
 Этот метод является устаревшим в платформа .NET Framework версии 2,0. Вместо этого используйте [ICorDebugEval2:: NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `elementType`  
 окне Значение перечисления Корелементтипе, указывающее тип элемента массива.  
  
 `pElementClass`  
 окне Указатель на объект ICorDebugClass, указывающий класс элемента. Это значение может быть равно null, если тип элемента является типом-примитивом.  
  
 `rank`  
 окне Число измерений массива. В платформа .NET Framework 2,0 это значение должно быть равно 1.  
  
 `dims`  
 окне Размер каждого измерения массива в байтах.  
  
 `lowBounds`  
 [в] Необязательно. Нижняя граница каждого измерения массива. Если это значение пропущено, для каждого измерения предполагается Нижняя граница, равная нулю.  
  
## <a name="remarks"></a>Remarks  

 Массив всегда создается в домене приложения, в котором в данный момент выполняется поток.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:** 1,1, 1,0
