---
description: 'Дополнительные сведения: метод ICorDebugFunction:: GetILCode'
title: Метод ICorDebugFunction::GetILCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
ms.openlocfilehash: 3b7bb29a028b189b24d3fbf02edc8190d9989a51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692528"
---
# <a name="icordebugfunctiongetilcode-method"></a>Метод ICorDebugFunction::GetILCode

Возвращает экземпляр ICorDebugCode, представляющий код на языке MSIL, связанный с данным объектом ICorDebugFunction.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppCode`  
 заполняет Указатель на `ICorDebugCode` экземпляр или значение null, если функция не была скомпилирована в MSIL.  
  
## <a name="remarks"></a>Remarks  

 Если функция "изменить и продолжить" была разрешена для этой функции, метод получит `GetILCode` код MSIL, соответствующий измененной версии кода этой функции в общеязыковой среде выполнения (CLR).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
