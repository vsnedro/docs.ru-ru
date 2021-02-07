---
description: 'Дополнительные сведения о методе: ICorDebugArrayValue:: Жетелементтипе'
title: Метод ICorDebugArrayValue::GetElementType
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementType
helpviewer_keywords:
- ICorDebugArrayValue::GetElementType method [.NET Framework debugging]
- GetElementType method [.NET Framework debugging]
ms.assetid: ed71961e-ae9b-4dfc-9554-06637696d697
topic_type:
- apiref
ms.openlocfilehash: 97c01a9c8ae7a1d73a1a15b97d3ce3e9aa079365
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723036"
---
# <a name="icordebugarrayvaluegetelementtype-method"></a>Метод ICorDebugArrayValue::GetElementType

Возвращает значение, указывающее простой тип элементов в массиве.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetElementType (  
    [out] CorElementType  *pType  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pType`  
 заполняет Указатель на значение перечисления Корелементтипе, указывающее тип.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
