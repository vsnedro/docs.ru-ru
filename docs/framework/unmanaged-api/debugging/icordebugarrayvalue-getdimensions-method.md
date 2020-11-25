---
title: Метод ICorDebugArrayValue::GetDimensions
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetDimensions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type:
- apiref
ms.openlocfilehash: bf498a14af3dccc7278155ecfc74132c2b519ed3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698199"
---
# <a name="icordebugarrayvaluegetdimensions-method"></a>Метод ICorDebugArrayValue::GetDimensions

Возвращает количество элементов в каждом измерении этого массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32          dims[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `cdim`  
 окне Число измерений данного объекта ICorDebugArrayValue.  
  
 Это значение также является размером `dims` массива, поскольку его размер равен числу измерений `ICorDebugArrayValue` объекта.  
  
 `dims`  
 заполняет Массив целых чисел, каждый из которых указывает количество элементов в измерении в этом `ICorDebugArrayValue` объекте.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
