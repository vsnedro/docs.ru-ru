---
title: Метод ICorDebugArrayValue::HasBaseIndicies
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.HasBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type:
- apiref
ms.openlocfilehash: e6e8eb91bbc41faf0dcea010da9aa54995058653
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894979"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a>Метод ICorDebugArrayValue::HasBaseIndicies
Возвращает значение, указывающее, имеют ли измерения данного массива базовый индекс, отличный от нуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbHasBaseIndicies`  
 заполняет Указатель на логическое значение, равное `true` , если одно или несколько измерений этого `ICorDebugArrayValue` объекта имеют базовый индекс, отличный от нуля; в противном случае логическое значение `false`—.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]
