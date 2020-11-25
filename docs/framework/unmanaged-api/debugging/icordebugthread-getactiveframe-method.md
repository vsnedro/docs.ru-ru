---
title: Метод ICorDebugThread::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
ms.openlocfilehash: 6ca4c1ad5ef575db075a5066146bacb6d1e59ea2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728086"
---
# <a name="icordebugthreadgetactiveframe-method"></a>Метод ICorDebugThread::GetActiveFrame

Возвращает указатель интерфейса на активный (самый последний) кадр для этого объекта ICorDebugThread.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppFrame`  
 заполняет Указатель на адрес объекта интерфейса ICorDebugFrame, который представляет кадр.  
  
## <a name="remarks"></a>Комментарии  

 `ppFrame`Если в настоящий момент нет активного кадра, параметр имеет значение null.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
