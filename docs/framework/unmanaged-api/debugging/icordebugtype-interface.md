---
title: Интерфейс ICorDebugType
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
ms.openlocfilehash: 9407dda7aab337f667cd5043b562d0eac94f0f04
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711927"
---
# <a name="icordebugtype-interface"></a>Интерфейс ICorDebugType

Представляет тип — базовый или сложный (то есть определяемый пользователем). Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateTypeParameters](icordebugtype-enumeratetypeparameters-method.md)|Возвращает указатель интерфейса на ICorDebugTypeEnum, который ссылается на универсальные <xref:System.Type> Параметры класса, на который ссылается this `ICorDebugType` .|  
|[Метод GetBase](icordebugtype-getbase-method.md)|Возвращает указатель интерфейса на объект `ICorDebugType` , который ссылается на базовый класс класса, на который ссылается этот класс `ICorDebugType` , если он существует.|  
|[Метод GetClass](icordebugtype-getclass-method.md)|Возвращает указатель интерфейса на объект ICorDebugClass, который ссылается на типизированный конструктор этого объекта `ICorDebugType` .|  
|[Метод GetFirstTypeParameter](icordebugtype-getfirsttypeparameter-method.md)|Возвращает указатель интерфейса на объект `ICorDebugType` , который ссылается на первый универсальный <xref:System.Type> параметр для конструктора класса, на который ссылается this `ICorDebugType` .|  
|[Метод GetRank](icordebugtype-getrank-method.md)|Возвращает число измерений в типе массива.|  
|[Метод GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md)|Возвращает указатель интерфейса на объект ICorDebugValue, содержащий значение статического поля, на которое ссылается заданный токен поля в указанном кадре стека.|  
|[Метод GetType](icordebugtype-gettype-method.md)|Возвращает значение Корелементтипе, описывающее собственный тип среды CLR, <xref:System.Type> на который ссылается this `ICorDebugType` .|  
  
## <a name="remarks"></a>Комментарии  

 Если тип является универсальным, `ICorDebugClass` представляет тип, не являющийся экземпляром. `ICorDebugType`Интерфейс представляет экземпляр универсального типа. Например, таблица Hashtable будет \<K, V> представлена с помощью `ICorDebugClass` , тогда как Hashtable будет \<Int32, String> представлена `ICorDebugType` .  
  
 Типы, не являющиеся универсальными, представлены как, так `ICorDebugClass` и `ICorDebugType` . Последний интерфейс появился в .NET Framework версии 2,0 для обработки создания экземпляра типа.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
