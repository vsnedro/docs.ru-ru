---
description: 'Дополнительные сведения: метод ICorDebugFrame:: Креатестеппер'
title: Метод ICorDebugFrame::CreateStepper
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
ms.openlocfilehash: 394418b89fd7a1c780a5bc33b97b8ef40bab8df2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693100"
---
# <a name="icordebugframecreatestepper-method"></a>Метод ICorDebugFrame::CreateStepper

Возвращает средство, позволяющее отладчику выполнять операции пошагового выполнения по отношению к этому ICorDebugFrame.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppStepper`  
 заполняет Указатель на адрес объекта ICorDebugStepper, который позволяет отладчику выполнять операции пошагового выполнения по отношению к текущему кадру.  
  
## <a name="remarks"></a>Remarks  

 Если кадр неактивен, объект средства Организации, как правило, должен вернуться к кадру до завершения этого шага.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
