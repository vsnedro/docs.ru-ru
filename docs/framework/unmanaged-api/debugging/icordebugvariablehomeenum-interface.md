---
description: 'Дополнительные сведения о: интерфейс ICorDebugVariableHomeEnum'
title: Интерфейс ICorDebugVariableHomeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum
helpviewer_keywords:
- ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type:
- apiref
ms.openlocfilehash: c56c68a6b5f9d329fe8af23f47b40fa629bfe3ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790624"
---
# <a name="icordebugvariablehomeenum-interface"></a>Интерфейс ICorDebugVariableHomeEnum

Предоставляет перечислитель для локальных переменных и аргументов в функции.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Следующий метод](icordebugvariablehomeenum-next-method.md)|Возвращает указанное число экземпляров [ICorDebugVariableHome](icordebugvariablehome-interface.md) , содержащих сведения о локальных переменных и аргументах в функции.|  
  
## <a name="remarks"></a>Remarks  

 `ICorDebugVariableHomeEnum`Интерфейс реализует интерфейс ICorDebugEnum.  
  
 `ICorDebugVariableHomeEnum`Экземпляр заполняется экземплярами [ICorDebugVariableHome](icordebugvariablehome-interface.md) путем вызова метода [ICorDebugCode4:: енумератевариаблехомес](icordebugcode4-enumeratevariablehomes-method.md) . Каждый экземпляр [ICorDebugVariableHome](icordebugvariablehome-interface.md) в коллекции представляет локальную переменную или аргумент в функции. Объекты  [ICorDebugVariableHome](icordebugvariablehome-interface.md) в коллекции можно перечислить, вызвав метод [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugVariableHome](icordebugvariablehome-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
