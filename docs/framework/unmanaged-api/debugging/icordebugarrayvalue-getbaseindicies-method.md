---
description: 'Дополнительные сведения о методе: ICorDebugArrayValue:: ЖетбасеиндиЦиес'
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
ms.openlocfilehash: ac38123860cc3187b7dc2398b32244387d19c5ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723126"
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
