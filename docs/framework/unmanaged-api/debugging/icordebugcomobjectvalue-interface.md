---
description: 'Дополнительные сведения о: интерфейс Икордебугкомобжектвалуе'
title: Интерфейс ICorDebugComObjectValue Interface
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
ms.openlocfilehash: 3c071c371ae6e330431630cfb1934b538d62efe6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710820"
---
# <a name="icordebugcomobjectvalue-interface"></a>Интерфейс ICorDebugComObjectValue Interface

Предоставляет методы для получения сведений, связанных с вызываемой оболочкой времени выполнения (RCW).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetCachedInterfacePointers](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|Возвращает необработанные указатели интерфейса, кэшированные в текущей RCW.|  
|[Метод GetCachedInterfaceTypes](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|Предоставляет перечислитель для типов интерфейса, к которым был применен регистр текущего объекта или использован в качестве.|  
  
## <a name="remarks"></a>Remarks  

 Чтобы проверить, представляет ли экземпляр интерфейса "ICorDebugValue" RCW, отладчик вызывает метод `QueryInterface` "ICorDebugValue" с `IID_ICorDebugComObjectValue` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
