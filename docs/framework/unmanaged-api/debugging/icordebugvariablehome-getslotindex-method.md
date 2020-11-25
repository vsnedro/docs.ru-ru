---
title: 'Метод ICorDebugVariableHome:: GetSlotIndex'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
ms.openlocfilehash: 4b071bd8e9d96084848c1553385eec5f8beca624
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711732"
---
# <a name="icordebugvariablehomegetslotindex-method"></a>Метод ICorDebugVariableHome:: GetSlotIndex

Возвращает управляемый индекс в виде слота локальной переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pSlotIndex`  
 заполняет Указатель на индекс в виде слота локальной переменной.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Метод возвращает следующие значения.  
  
|Значение|Описание|  
|-----------|-----------------|  
|`S_OK`|Вызов метода вернул значение индекса слота в `pSlotIndex` .|  
|`E_FAIL`|Текущий экземпляр [ICorDebugVariableHome](icordebugvariablehome-interface.md) представляет аргумент функции.|  
  
## <a name="remarks"></a>Комментарии  

 Чтобы получить метаданные для этой локальной переменной, можно использовать индекс Slot.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugVariableHome](icordebugvariablehome-interface.md)
