---
description: 'Дополнительные сведения о методе: ICorDebugProcess6::P Роцессстатечанжед'
title: Метод ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 8060c29598adf5d4bbe7bffb4cd6611ee19a2669
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691371"
---
# <a name="icordebugprocess6processstatechanged-method"></a>Метод ICorDebugProcess6::ProcessStateChanged

Уведомляет [ICorDebug](icordebug-interface.md) о том, что процесс выполняется.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a>Параметры  

 `change`  
 окне Член перечисления [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)  
  
## <a name="remarks"></a>Remarks  

 Отладчик вызывает этот метод, чтобы уведомить [ICorDebug](icordebug-interface.md) о том, что процесс выполняется.  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess6](icordebugprocess6-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
