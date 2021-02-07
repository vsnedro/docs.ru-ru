---
description: 'Дополнительные сведения о методе: ICorDebugEval2:: Креатевалуефортипе'
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
ms.openlocfilehash: 2a8cd129d6194a4870817eb64b79606c395cb055
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693919"
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

 `CreateValueForType` обобщает [ICorDebugEval:: креатевалуе](icordebugeval-createvalue-method.md) , позволяя указать произвольный тип объекта, включая сконструированные типы, такие как `List<int>` . Единственная цель этого метода — создать значение, которое может быть передано в вычисление функции.  
  
 Тип должен быть классом или типом значения. Этот метод нельзя использовать для создания значений массива или строковых значений.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
