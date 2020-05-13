---
title: Метод ICorDebugType::GetBase
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
ms.openlocfilehash: fc406f6e87e5b2be48c6fe7d5fc988774ac5cd11
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379987"
---
# <a name="icordebugtypegetbase-method"></a>Метод ICorDebugType::GetBase
Возвращает указатель интерфейса на объект ICorDebugType, представляющий базовый тип, если он существует, типа, представленного этим объектом `ICorDebugType` .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pBase`  
 заполняет Указатель на адрес `ICorDebugType` объекта, который представляет базовый тип.  
  
## <a name="remarks"></a>Remarks  
 Поиск базового типа для типа полезен для реализации общих функциональных возможностей отладчика, таких как вывод всех полей объекта или его родительских классов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
