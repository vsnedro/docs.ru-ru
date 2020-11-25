---
title: Метод ICorDebugThread::GetActiveChain
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
ms.openlocfilehash: e6b1d78b2bd95ea27f4b19a045cd2680342e8a80
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728099"
---
# <a name="icordebugthreadgetactivechain-method"></a>Метод ICorDebugThread::GetActiveChain

Возвращает указатель интерфейса на активную (последнюю) цепь стека на этом объекте ICorDebugThread.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppChain`  
 заполняет Указатель на адрес объекта ICorDebugChain, который представляет цепочку стека.  
  
## <a name="remarks"></a>Комментарии  

 `ppChain`Параметр имеет значение null, если цепочка стека в данный момент не активна.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
