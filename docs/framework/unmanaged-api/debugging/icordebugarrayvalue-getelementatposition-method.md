---
description: 'Дополнительные сведения о методе: ICorDebugArrayValue:: GetElementAtPosition'
title: Метод ICorDebugArrayValue::GetElementAtPosition
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementAtPosition
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementAtPosition
helpviewer_keywords:
- GetElementAtPosition method [.NET Framework debugging]
- ICorDebugArrayValue::GetElementAtPosition method [.NET Framework debugging]
ms.assetid: 6fd5eaa4-1997-4910-82f5-3887480db764
topic_type:
- apiref
ms.openlocfilehash: ef8e4a39f5fe4088b1883803aee037c51f410241
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723040"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a>Метод ICorDebugArrayValue::GetElementAtPosition

Возвращает элемент в заданной позиции, рассматривая массив как одномерный массив с отсчетом от нуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `nPosition`  
 окне Расположение извлекаемого элемента.  
  
 `ppValue`  
 заполняет Указатель на адрес объекта ICorDebugValue, который представляет значение элемента.  
  
## <a name="remarks"></a>Remarks  

 Компоновка многомерного массива соответствует стилю в C++ для макета массива.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
