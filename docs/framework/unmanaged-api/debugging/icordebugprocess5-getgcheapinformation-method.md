---
description: 'Дополнительные сведения о методе: метод ICorDebugProcess5:: GetGCHeapInformation'
title: Метод ICorDebugProcess5::GetGCHeapInformation
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
ms.openlocfilehash: e63f8871a2c18d6daf2dcf93b92e49123c56442f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649811"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a>Метод ICorDebugProcess5::GetGCHeapInformation

Содержит общие сведения о куче сборки мусора, включая возможность перечисления в данный момент.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pHeapInfo`  
 заполняет Указатель на [COR_HEAPINFO](cor-heapinfo-structure.md) значение, предоставляющее общие сведения о куче сборки мусора.  
  
## <a name="remarks"></a>Remarks  

 `ICorDebugProcess5::GetGCHeapInformation`Перед перечислением областей кучи или отдельных куч необходимо вызвать метод, чтобы убедиться в том, что структуры сборки мусора в этом процессе являются допустимыми. Невозможно выполнить обход кучи сборки мусора, пока выполняется сбор. В противном случае перечисление может собирать недопустимые структуры сборки мусора.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
