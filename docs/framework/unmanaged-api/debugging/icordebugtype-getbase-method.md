---
description: 'Дополнительные сведения о методе "ICorDebugType:: Polybase"'
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
ms.openlocfilehash: 78cd540974b540b704e946f6c723214d72e89ab4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658390"
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
