---
title: Интерфейс ICorDebugClass
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
ms.openlocfilehash: 4f488741f4233f06c128e0a262ce798ef27af3ff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699642"
---
# <a name="icordebugclass-interface"></a>Интерфейс ICorDebugClass

Представляет тип, который может быть базовым или сложным (иными словами, пользовательским). Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetModule](icordebugclass-getmodule-method.md)|Возвращает модуль, который определяет этот класс.|  
|[Метод GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md)|Возвращает значение указанного статического поля.|  
|[Метод GetToken](icordebugclass-gettoken-method.md)|Возвращает `TypeDef` маркер метаданных для этого класса.|  
  
## <a name="remarks"></a>Комментарии  

 `ICorDebugClass`Интерфейс представляет универсальный тип, экземпляр которого не был создан. Интерфейс ICorDebugType представляет экземпляр универсального типа. Например, будет `Hashtable<K, V>` представлено `ICorDebugClass` , а будет `Hashtable<Int32, String>` представлено `ICorDebugType` .  
  
 Типы, не являющиеся универсальными, представлены как, так `ICorDebugClass` и `ICorDebugType` . Последний интерфейс появился в .NET Framework версии 2,0 для обработки создания экземпляра типа.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
