---
description: 'Дополнительные сведения: метод ICorDebugCode:: Жетверсионнумбер'
title: Метод ICorDebugCode::GetVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
ms.openlocfilehash: 901342333bea3d455407602dde78bdccd0140d77
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764909"
---
# <a name="icordebugcodegetversionnumber-method"></a>Метод ICorDebugCode::GetVersionNumber

Возвращает номер, отсчитываемый от единицы, определяющий версию кода, который представляет этот "ICorDebugCode".

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetVersionNumber (
    [out] ULONG32    *nVersion
);
```

## <a name="parameters"></a>Параметры

 `nVersion`  
 заполняет Указатель на номер версии кода.

## <a name="remarks"></a>Remarks

 Номер версии увеличивается каждый раз, когда в коде выполняется операция "изменить и продолжить" (EnC).

## <a name="requirements"></a>Требования

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
