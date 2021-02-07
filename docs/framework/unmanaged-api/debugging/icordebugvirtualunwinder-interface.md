---
description: 'Дополнительные сведения о: интерфейс ICorDebugVirtualUnwinder'
title: Интерфейс ICorDebugVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: e941ace2e7f72c9f7956c03bae19f9b92094b338
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738082"
---
# <a name="icordebugvirtualunwinder-interface"></a>Интерфейс ICorDebugVirtualUnwinder

Предоставляет методы, помогающие очистить стек.  
  
## <a name="methods"></a>Методы  
  
|Метод|Имя|  
|------------|----------|  
|[Метод GetContext](icordebugvirtualunwinder-getcontext-method.md)|Получает текущий контекст этого средства очистки.|  
|[Следующий метод](icordebugvirtualunwinder-next-method.md)|Переходит в контекст вызывающего объекта.|  
  
## <a name="remarks"></a>Remarks  

 Элементы интерфейса `ICorDebugVirtualUnwinder` реализуются отладчиком для упрощения очистки стека.  
  
> [!NOTE]
> Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
