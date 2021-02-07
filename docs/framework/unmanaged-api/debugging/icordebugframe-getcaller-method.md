---
description: 'Дополнительные сведения о методе ICorDebugFrame:: вызывали'
title: Метод ICorDebugFrame::GetCaller
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
ms.openlocfilehash: a042341f6edfa0e8f6ca00f758107852f9e381cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693048"
---
# <a name="icordebugframegetcaller-method"></a>Метод ICorDebugFrame::GetCaller

Возвращает указатель на объект ICorDebugFrame в текущей цепочке, вызвавшей этот кадр.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppFrame`  
 заполняет Указатель на адрес `ICorDebugFrame` объекта, представляющий вызывающий кадр. Это значение равно null, если вызываемый кадр является самым внешним кадром в текущей цепочке.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
