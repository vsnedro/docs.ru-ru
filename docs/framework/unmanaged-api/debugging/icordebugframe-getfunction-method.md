---
description: 'Дополнительные сведения о методе ICorDebugFrame:: Function'
title: Метод ICorDebugFrame::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
ms.openlocfilehash: 0309a066f686e55d086de1cbb040eea58e031df3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692996"
---
# <a name="icordebugframegetfunction-method"></a>Метод ICorDebugFrame::GetFunction

Возвращает функцию, содержащую код, связанный с данным кадром стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppFunction`  
 заполняет Указатель на адрес объекта ICorDebugFunction, представляющего функцию, содержащую код, связанный с данным кадром стека.  
  
## <a name="remarks"></a>Remarks  

 `GetFunction`Метод может завершиться ошибкой, если фрейм не связан с какой-либо определенной функцией.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
