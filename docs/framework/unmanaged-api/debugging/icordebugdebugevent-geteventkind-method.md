---
title: Метод ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 7876dc6ec5ecee52b64e54e1c42533f8348e4dc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713682"
---
# <a name="icordebugdebugeventgeteventkind-method"></a>Метод ICorDebugDebugEvent::GetEventKind

Указывает тип события, который представляет этот объект `ICorDebugDebugEvent`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a>Параметры  

 pDebugEventKind  
 Указатель на элемент перечисления [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) , указывающий тип события.  
  
## <a name="remarks"></a>Комментарии  

 На основе значения `pDebugEventKind` можно вызвать `QueryInterface`, чтобы получить более точный интерфейс событий отладки, содержащий дополнительные данные.  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugDebugEvent](icordebugdebugevent-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
