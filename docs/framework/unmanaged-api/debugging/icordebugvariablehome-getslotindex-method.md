---
description: 'Дополнительные сведения о методе: ICorDebugVariableHome:: GetSlotIndex'
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
ms.openlocfilehash: 7f6ee01c2bfcee4c78f8463a7cefac1f90a3295f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790650"
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
  
## <a name="remarks"></a>Remarks  

 Чтобы получить метаданные для этой локальной переменной, можно использовать индекс Slot.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugVariableHome](icordebugvariablehome-interface.md)
