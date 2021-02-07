---
description: 'Дополнительные сведения о методе: ICorDebugReferenceValue:: IsNull'
title: Метод ICorDebugReferenceValue::IsNull
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.IsNull
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::IsNull
helpviewer_keywords:
- IsNull method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::IsNull method [.NET Framework debugging]
ms.assetid: 99e8c8d7-a1c0-47c8-9dbd-03e0b2bcb4d5
topic_type:
- apiref
ms.openlocfilehash: 9fffc869e20d1d3aa3a347ff2e026e6b55e6bd4f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691033"
---
# <a name="icordebugreferencevalueisnull-method"></a>Метод ICorDebugReferenceValue::IsNull

Возвращает значение, указывающее, является ли ICorDebugReferenceValue значением NULL, в этом случае параметр не `ICorDebugReferenceValue` указывает на объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pbNull`  
 заполняет Указатель на логическое значение, равное, `true` Если этот `ICorDebugReferenceValue` объект имеет значение NULL; в противном случае `pbNull` — `false` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
