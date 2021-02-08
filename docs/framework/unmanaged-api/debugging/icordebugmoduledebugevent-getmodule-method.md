---
description: 'Дополнительные сведения о методе: Икордебугмодуледебужевент:: module'
title: Метод ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: c6d7171da231576ff90f54aaefe4b473af0afd40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790741"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a>Метод ICorDebugModuleDebugEvent::GetModule

Возвращает объединенный модуль, который только что был загружен или выгружен.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppModule`  
 [out] Указатель на адрес объекта ICorDebugModule, представляющего объединенный модуль, который был только что загружен или выгружен.  
  
## <a name="remarks"></a>Remarks  

 Можно вызвать метод [GetEventKind](icordebugdebugevent-geteventkind-method.md) , чтобы определить, был ли модуль загружен или выгружен.  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
