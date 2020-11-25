---
title: 'Метод ICorDebugVariableHome:: методом offset'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
ms.openlocfilehash: c5d491b66e4ec64dffa4e19dabff876c9c473036
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711797"
---
# <a name="icordebugvariablehomegetoffset-method"></a>Метод ICorDebugVariableHome:: методом offset

Возвращает смещение от базового регистра для переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pOffset`  
 заполняет Смещение от базового регистра.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Метод возвращает следующие значения:  
  
|Значение|Описание|  
|-----------|-----------------|  
|`S_OK`|Переменная находится в расположении в памяти относительно регистра.|  
|`E_FAIL`|Переменная не находится в расположении в памяти относительно регистра.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugVariableHome](icordebugvariablehome-interface.md)
