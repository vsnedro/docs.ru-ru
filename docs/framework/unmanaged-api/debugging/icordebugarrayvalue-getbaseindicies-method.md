---
title: Метод ICorDebugArrayValue::GetBaseIndicies
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type:
- apiref
ms.openlocfilehash: ea5c5a728afb9ac90f8599c833caab11fd0c65fe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731466"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a>Метод ICorDebugArrayValue::GetBaseIndicies

Возвращает базовый индекс каждого измерения в массиве.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `cdim`  
 окне Число измерений данного `ICorDebugArrayValue` объекта. Это значение также является размером `indicies` массива, поскольку его размер равен числу измерений `ICorDebugArrayValue` объекта.  
  
 `indicies`  
 заполняет Массив целых чисел, каждый из которых является базовым индексом (т. е. начальным индексом) измерения этого `ICorDebugArrayValue` объекта.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
