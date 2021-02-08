---
description: 'Дополнительные сведения о: интерфейс ICorDebugVariableSymbol'
title: Интерфейс ICorDebugVariableSymbol
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: fa3fc1f318627e9175a3066c3bd3eac00929ea60
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790546"
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
  
## <a name="remarks"></a>Remarks  
  
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
