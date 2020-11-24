---
title: Интерфейс ICorDebugVariableSymbol
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 3d808fd49eb7767f1f48ad4e07d8ba7e47c8f34b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679485"
---
# <a name="icordebugvariablesymbol-interface"></a>Интерфейс ICorDebugVariableSymbol

Извлекает сведения символа отладки для статического поля.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetName](icordebugvariablesymbol-getname-method.md)|Получает имя переменной.|  
|[Метод GetSize](icordebugvariablesymbol-getsize-method.md)|Получает размер переменной в байтах.|  
|[Метод GetSlotIndex](icordebugvariablesymbol-getslotindex-method.md)|Возвращает управляемый индекс слота локальной переменной.|  
|[Метод GetValue](icordebugvariablesymbol-getvalue-method.md)|Возвращает значение переменной в виде массива байтов.|  
|[Метод SetValue](icordebugvariablesymbol-setvalue-method.md)|Присваивает переменной значение массива байтов.|  
  
## <a name="remarks"></a>Комментарии  
  
> [!NOTE]
> Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
