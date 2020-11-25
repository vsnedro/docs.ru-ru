---
title: Метод ICorDebugModule2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
ms.openlocfilehash: cfa6df7a812559f05a4c57381a5007c9c90238e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709665"
---
# <a name="icordebugmodule2setjmcstatus-method"></a>Метод ICorDebugModule2::SetJMCStatus

Устанавливает состояние Только мой код (JMC) всех методов всех классов данного ICorDebugModule2 в указанное значение, за исключением тех, `pTokens` которые в массиве задаются в противоположном значении.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `bIsJustMycode`  
 окне Задайте значение `true` , если код должен быть отлажен; в противном случае — значение `false` .  
  
 `cTokens`  
 [in] Размер массива `pTokens`.  
  
 `pTokens`  
 окне Массив `mdToken` значений, каждый из которых ссылается на метод, для которого в качестве его состояния JMC задано значение! `bIsJustMycode` .  
  
## <a name="remarks"></a>Комментарии  

 Состояние JMC каждого метода, указанного в `pTokens` массиве, устанавливается равным противоположному `bIsJustMycode` значению. Состояние всех остальных методов этого модуля задается равным `bIsJustMycode` значению.  
  
 `SetJMCStatus`Метод удаляет все предыдущие параметры JMC в этом модуле.  
  
 `SetJMCStatus`Метод возвращает S_OK HRESULT, если все функции заданы успешно. Он возвращает CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT, если некоторые функции, которые помечены, `true` не могут быть отлажены.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
