---
description: 'Дополнительные сведения о методе: ICorDebugDebugEvent:: GetEventKind'
title: Метод ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 9e15eb82195fae8aa3797ea47cb04d0bb407d2ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764324"
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
  
## <a name="remarks"></a>Remarks  

 На основе значения `pDebugEventKind` можно вызвать `QueryInterface`, чтобы получить более точный интерфейс событий отладки, содержащий дополнительные данные.  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugDebugEvent](icordebugdebugevent-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
