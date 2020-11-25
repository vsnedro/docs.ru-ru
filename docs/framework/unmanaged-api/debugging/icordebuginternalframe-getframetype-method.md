---
title: Метод ICorDebugInternalFrame::GetFrameType
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame.GetFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type:
- apiref
ms.openlocfilehash: c675ba4b56cecd1990184cd2f0e805250c3dfeb7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724888"
---
# <a name="icordebuginternalframegetframetype-method"></a>Метод ICorDebugInternalFrame::GetFrameType

Возвращает тип этого внутреннего кадра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pType`  
 заполняет Указатель на значение перечисления CorDebugInternalFrameType, указывающее тип внутреннего кадра, представленного этим `ICorDebugInternalFrame` объектом.  
  
## <a name="remarks"></a>Комментарии  

 Тип внутреннего кадра никогда не будет STUBFRAME_NONE. Отладчики должны корректно пропускать нераспознаваемые типы внутренних кадров.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
