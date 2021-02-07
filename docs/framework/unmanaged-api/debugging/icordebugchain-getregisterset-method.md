---
description: 'Дополнительные сведения о методе: ICorDebugChain::/Register'
title: Метод ICorDebugChain::GetRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetRegisterSet
helpviewer_keywords:
- ICorDebugChain::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: bc4288b6-3331-4ae3-990d-e1d6e62ecb67
topic_type:
- apiref
ms.openlocfilehash: 75c77838cb4ef49dd922a4e39b41e622693e928d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694960"
---
# <a name="icordebugchaingetregisterset-method"></a>Метод ICorDebugChain::GetRegisterSet

Возвращает набор регистров для активной части этой цепочки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppRegisters`  
 заполняет Указатель на адрес объекта [ICorDebugRegisterSet](icordebugregisterset-interface.md) , который представляет набор регистров для активной части этой цепочки.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
