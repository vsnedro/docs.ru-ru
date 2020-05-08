---
title: Метод ICorDebugEval2::NewParameterizedArray
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type:
- apiref
ms.openlocfilehash: 9d589bfc3093d03d87acb47ade0fc6c972bcd335
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976113"
---
# <a name="icordebugeval2newparameterizedarray-method"></a>Метод ICorDebugEval2::NewParameterizedArray
Выделяет новый массив указанного типа элемента и измерений.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pElementType`  
 окне Указатель на объект ICorDebugType, представляющий тип элемента, хранящегося в массиве.  
  
 `rank`  
 окне Число измерений массива. В .NET Framework версии 2,0 это значение должно быть равно 1.  
  
 `dims`  
 окне Размер каждого измерения массива в байтах.  
  
 `lowBounds`  
 [в] Необязательно. Нижняя граница каждого измерения массива. Если это значение пропущено, для каждого измерения предполагается Нижняя граница, равная нулю.  
  
## <a name="remarks"></a>Remarks  
 Элементы массива могут быть экземплярами универсального типа. Массив всегда создается в домене приложения, в котором в данный момент выполняется поток. В .NET Framework 2,0 значение `rank` должно быть равно 1.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
