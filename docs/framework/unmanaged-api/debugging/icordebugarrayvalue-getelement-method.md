---
description: 'Дополнительные сведения о методе: ICorDebugArrayValue:: WebMethod'
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
ms.openlocfilehash: dfae074b78735934d1e71b13ce01c24741a5f2ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723066"
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
