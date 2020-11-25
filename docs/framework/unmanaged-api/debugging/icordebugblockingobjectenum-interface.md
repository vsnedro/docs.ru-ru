---
title: Интерфейс ICorDebugBlockingObjectEnum
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum
helpviewer_keywords:
- ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type:
- apiref
ms.openlocfilehash: 221acf9bea714728a81b9f15c8165c1f9eba16a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719207"
---
# <a name="icordebugblockingobjectenum-interface"></a>Интерфейс ICorDebugBlockingObjectEnum

Предоставляет перечислитель для списка структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) . Этот интерфейс является подклассом интерфейса ICorDebugEnum.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Next](icordebugblockingobjectenum-next-method.md)|Перечисляет по списку структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) .|  
  
## <a name="remarks"></a>Комментарии  

 Каждая структура `CorDebugBlockingObject` представляет объект, блокирующий поток.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
