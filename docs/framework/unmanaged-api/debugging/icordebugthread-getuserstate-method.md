---
title: Метод ICorDebugThread::GetUserState
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetUserState
helpviewer_keywords:
- GetUserState method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetUserState method [.NET Framework debugging]
ms.assetid: ae0cfd73-8ead-4d36-9310-dccaac9db0bd
topic_type:
- apiref
ms.openlocfilehash: dd3936656ce1c9482b7f07a5780fcf651356b4be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727969"
---
# <a name="icordebugthreadgetuserstate-method"></a>Метод ICorDebugThread::GetUserState

Возвращает текущее пользовательское состояние этого ICorDebugThread.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pState`  
 заполняет Указатель на побитовую комбинацию значений перечисления Кордебугусерстате, описывающих текущее пользовательское состояние этого потока.  
  
## <a name="remarks"></a>Комментарии  

 Пользовательское состояние потока — это состояние потока, которое проверяется отлаживаемой программой. Для потока может быть задано несколько битов состояния.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
