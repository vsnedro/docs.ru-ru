---
title: Метод ICorDebugStepper::SetRangeIL
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetRangeIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetRangeIL
helpviewer_keywords:
- SetRangeIL method [.NET Framework debugging]
- ICorDebugStepper::SetRangeIL method [.NET Framework debugging]
ms.assetid: a20c95f0-6da7-4b41-b27f-584211cebb92
topic_type:
- apiref
ms.openlocfilehash: 5a27f155021661022b27022bbb252e00dfa67255
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698784"
---
# <a name="icordebugsteppersetrangeil-method"></a>Метод ICorDebugStepper::SetRangeIL

Задает значение, указывающее, будут ли вызовы метода [ICorDebugStepper:: степранже](icordebugstepper-steprange-method.md) передавать значения аргумента, которые относятся к машинному коду или по коду языка MSIL в методе, через который выполняется пошаговое выполнение.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `bIL`  
 окне Задайте значение, `true` чтобы указать, что диапазоны зависят от кода MSIL. Задайте значение, `false` чтобы указать, что диапазоны зависят от машинного кода. Значение по умолчанию — `true`.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
