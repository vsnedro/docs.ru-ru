---
title: Метод ICorDebugEval2::CreateValueForType
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
ms.openlocfilehash: fd7acaa8bcb4d53893855bcd25ff68cf26e30354
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976165"
---
# <a name="icordebugeval2createvaluefortype-method"></a>Метод ICorDebugEval2::CreateValueForType
Возвращает указатель на новый объект ICorDebugValue указанного типа с начальным значением нуль или null.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pType`  
 окне Указатель на объект ICorDebugType, представляющий тип.  
  
 `ppValue`  
 заполняет Указатель на адрес `ICorDebugValue` объекта, представляющий значение.  
  
## <a name="remarks"></a>Remarks  
 `CreateValueForType`обобщает [ICorDebugEval:: креатевалуе](icordebugeval-createvalue-method.md) , позволяя указать произвольный тип объекта, включая сконструированные типы, такие `List<int>`как. Единственная цель этого метода — создать значение, которое может быть передано в вычисление функции.  
  
 Тип должен быть классом или типом значения. Этот метод нельзя использовать для создания значений массива или строковых значений.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
