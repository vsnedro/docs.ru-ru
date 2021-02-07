---
description: 'Дополнительные сведения о методе: ICorDebugChain:: Thread'
title: Метод ICorDebugChain::GetThread
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type:
- apiref
ms.openlocfilehash: 090cb40c3681792ce4a30cd342e65dc02ac3f381
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694927"
---
# <a name="icordebugchaingetthread-method"></a>Метод ICorDebugChain::GetThread

Возвращает физический поток, частью которого является эта цепочка вызовов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppThread`  
 заполняет Указатель на объект ICorDebugThread, представляющий физический поток, частью которого является эта цепочка вызовов.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
