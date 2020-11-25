---
title: Метод ICorDebugCode::CreateBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
ms.openlocfilehash: ade428ce001a6b40e2fed67f4f23b12cef5ea30f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717661"
---
# <a name="icordebugcodecreatebreakpoint-method"></a>Метод ICorDebugCode::CreateBreakpoint

Создает точку останова в этом сегменте кода в указанном смещении.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `offset`  
 окне Смещение для создания точки останова.  
  
 `ppBreakpoint`  
 заполняет Указатель на адрес объекта "ICorDebugFunctionBreakpoint", представляющего точку останова.  
  
## <a name="remarks"></a>Комментарии  

 Прежде чем точка останова станет активной, ее необходимо добавить в объект Process.  
  
 Если этот код является кодом на языке MSIL и имеется JIT-скомпилированная собственная версия кода, то точка останова будет применена и в JIT-скомпилированном коде. (То же самое верно, если код компилируется позже.)  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
