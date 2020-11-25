---
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
ms.openlocfilehash: 1bbcbcfbb78d421f247a13f58070b68f701e4ed1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697224"
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
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
