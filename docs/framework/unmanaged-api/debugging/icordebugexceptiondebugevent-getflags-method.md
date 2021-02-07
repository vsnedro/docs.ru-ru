---
description: 'Дополнительные сведения о методе: Икордебужексцептиондебужевент:: "Flags"'
title: Метод ICorDebugExceptionDebugEvent::GetFlags
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 54a6c9b0dff2346ca130f80e72fe06dbb3017f10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693477"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a>Метод ICorDebugExceptionDebugEvent::GetFlags

Возвращает флаг, указывающий, может ли исключение быть перехвачено.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pdwFlags`  
 заполняет Указатель на значение [кордебужексцептионфлагс](cordebugexceptionflags-enumeration.md) , указывающее, может ли быть перехвачено исключение.  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
