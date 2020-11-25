---
title: Метод ICorDebugArrayValue::GetElement
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElement
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type:
- apiref
ms.openlocfilehash: 0b6b6f46c7fff8f1d4c2ad555c93423f9ca8ac09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698155"
---
# <a name="icordebugarrayvaluegetelement-method"></a>Метод ICorDebugArrayValue::GetElement

Возвращает значение заданного элемента массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `cdim`  
 окне Число измерений данного `ICorDebugArrayValue` объекта.  
  
 Это значение также является размером `indices` массива, поскольку его размер равен числу измерений `ICorDebugArrayValue` объекта.  
  
 `indices`  
 окне Массив значений индекса, каждый из которых задает позиции в измерении `ICorDebugArrayValue` объекта.  
  
 Это значение не должно быть равно NULL.  
  
 `ppValue`  
 заполняет Указатель на адрес объекта ICorDebugValue, представляющий значение указанного элемента.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
