---
description: 'Дополнительные сведения о: интерфейс ICorDebugCode4'
title: Интерфейс ICorDebugCode4
ms.date: 03/30/2017
api_name:
- ICorDebugCode4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4
helpviewer_keywords:
- ICorDebugCode4 interface [.NET Framework debugging]
ms.assetid: a3fdf523-274a-449c-920b-9fcb0aed1d97
topic_type:
- apiref
ms.openlocfilehash: 1276db5c55c3d98e5ffa379f6126f700d93c1670
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764727"
---
# <a name="icordebugcode4-interface"></a>Интерфейс ICorDebugCode4

Предоставляет метод, позволяющий отладчику перечислить локальные переменные и аргументы в функции.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md)|Возвращает перечислитель для локальных переменных и аргументов в функции.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugCode3](icordebugcode3-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
