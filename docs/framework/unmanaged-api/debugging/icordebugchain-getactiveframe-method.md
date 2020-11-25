---
title: Метод ICorDebugChain::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
ms.openlocfilehash: daecd216b4d7e9c23336b8956c13735549be901b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730140"
---
# <a name="icordebugchaingetactiveframe-method"></a>Метод ICorDebugChain::GetActiveFrame

Возвращает активный (то есть самый последний) кадр в цепочке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppFrame`  
 заполняет Указатель на адрес объекта ICorDebugFrame, который представляет активный (то есть самый последний) кадр в цепочке.  
  
## <a name="remarks"></a>Комментарии  

 Если управляемый фрейм стека недоступен, `ppFrame` устанавливается в значение null.  
  
 Если активный кадр недоступен, вызов будет выполнен и `ppFrame` будет иметь значение null. Активные фреймы не будут доступны для цепочек, инициированных из-за CHAIN_ENTER_UNMANAGED, и для некоторых цепочек, инициированных из-за CHAIN_CLASS_INIT. См. раздел перечисление Кордебугчаинреасон.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
