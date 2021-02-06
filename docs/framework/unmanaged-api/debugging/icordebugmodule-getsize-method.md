---
description: 'Дополнительные сведения о методе: ICorDebugModule:: resize'
title: Метод ICorDebugModule::GetSize
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
ms.openlocfilehash: b2179c8830911e417ccd482fe72438c4cd7fd3df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660158"
---
# <a name="icordebugmodulegetsize-method"></a>Метод ICorDebugModule::GetSize

Возвращает размер модуля (в байтах).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pcBytes`  
 заполняет Размер модуля в байтах.  
  
 Если модуль был создан из генератора образов в машинном кодах (NGen.exe), размер модуля будет равен нулю.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
