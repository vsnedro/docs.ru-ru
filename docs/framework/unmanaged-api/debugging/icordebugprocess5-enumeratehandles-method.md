---
title: Метод ICorDebugProcess5::EnumerateHandles
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
ms.openlocfilehash: 607847180cca039d4c71f26e446a17a14dc2fb9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724342"
---
# <a name="icordebugprocess5enumeratehandles-method"></a>Метод ICorDebugProcess5::EnumerateHandles

Возвращает перечислитель для дескрипторов объектов в процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a>Параметры  

 `types`  
 окне Побитовое сочетание значений [CorGCReferenceType](corgcreferencetype-enumeration.md) , определяющих тип дескрипторов, включаемых в коллекцию.  
  
 `ppENum`  
 заполняет Указатель на адрес [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) , который является перечислителем для объектов, которые должны быть собраны в мусор.  
  
## <a name="remarks"></a>Комментарии  

 `EnumerateHandles` — Это вспомогательная функция, которая поддерживает проверку таблицы Handle. Он похож на метод [метод ICorDebugProcess5:: енумератегкреференцес](icordebugprocess5-enumerategcreferences-method.md) , за исключением того, что вместо заполнения коллекции [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) всеми объектами, которые должны быть собраны сборщиком мусора, он включает только объекты, имеющие дескрипторы из таблицы дескрипторов.  
  
 `types`Параметр задает типы обработчиков для включения в коллекцию. `types` может быть любым из следующих трех членов перечисления [CorGCReferenceType](corgcreferencetype-enumeration.md) :  
  
- `CorHandleStrongOnly` (обрабатывает только строгие ссылки).  
  
- `CorHandleWeakOnly` (дескрипторы только для слабых ссылок).  
  
- `CorHandleAll` (все дескрипторы).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
