---
description: 'Дополнительные сведения о методе: ICorDebugStepper2:: SetJMC'
title: Метод ICorDebugStepper2::SetJMC
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2.SetJMC
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type:
- apiref
ms.openlocfilehash: 07178ab90bb392e64c9d8a8fddf961efbb268002
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717541"
---
# <a name="icordebugstepper2setjmc-method"></a>Метод ICorDebugStepper2::SetJMC

Задает значение, указывающее, следует ли выполнить шаги для этого параметра ICorDebugStepper только с помощью кода, созданного разработчиком приложения. Этот процесс также известен как отладка "только мой код" (JMC).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `fIsJMCStepper`  
 окне Установите в значение `true` только для шага с помощью кода, созданного разработчиком приложения; в противном случае задайте для значение `false` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
