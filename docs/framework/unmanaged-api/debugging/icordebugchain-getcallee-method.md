---
description: 'Дополнительные сведения о методе: ICorDebugChain:: Зовите.'
title: Метод ICorDebugChain::GetCallee
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
ms.openlocfilehash: 4787893c86804c648dae14bf2e6f7425808104b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661432"
---
# <a name="icordebugchaingetcallee-method"></a>Метод ICorDebugChain::GetCallee

Возвращает цепочку, вызванную этой цепочкой.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppChain`  
 заполняет Указатель на адрес объекта ICorDebugChain, который представляет вызываемую цепочку. Если эта цепочка выполняется в данный момент (то есть если эта цепочка не ожидает возврата вызванной цепочки), `ppChain` будет иметь значение null.  
  
## <a name="remarks"></a>Remarks  

 Эта цепочка будет ожидать возврата вызванной цепочки перед возобновлением выполнения. Вызываемая цепочка может находиться в другом потоке в случае маршалинга вызовов между потоками.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
