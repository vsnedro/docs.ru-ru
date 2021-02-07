---
description: 'Дополнительные сведения о методе: ICorDebugChain:: GetStackRange'
title: Метод ICorDebugChain::GetStackRange
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
ms.openlocfilehash: 066dda06564655350d799dabb54acd622b828172
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694934"
---
# <a name="icordebugchaingetstackrange-method"></a>Метод ICorDebugChain::GetStackRange

Возвращает диапазон адресов сегмента стека для этой цепочки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pStart`  
 заполняет Указатель на `CORDB_ADDRESS` значение, которое является начальным адресом сегмента стека.  
  
 `pEnd`  
 заполняет Указатель на `CORDB_ADDRESS` значение, которое является конечным адресом сегмента стека.  
  
## <a name="remarks"></a>Remarks  

 Числовой диапазон имеет смысл только для сравнения расположений в кадрах стека. Вы не можете делать предположения о том, что фактически хранится в стеке.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
