---
title: Интерфейс ICorDebugAppDomain2
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
ms.openlocfilehash: f20ae6977504f958b7bfa8e2f073b7db6e8b822b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731479"
---
# <a name="icordebugappdomain2-interface"></a>Интерфейс ICorDebugAppDomain2

Предоставляет методы для работы с массивами, указателями, указателями функций и ссылочными типами. Этот интерфейс является расширением интерфейса ICorDebugAppDomain.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetArrayOrPointerType](icordebugappdomain2-getarrayorpointertype-method.md)|Возвращает массив указанного типа или указатель или ссылку на указанный тип.|  
|[Метод GetFunctionPointerType](icordebugappdomain2-getfunctionpointertype-method.md)|Возвращает указатель на функцию с заданной сигнатурой.|  
  
## <a name="remarks"></a>Комментарии  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
