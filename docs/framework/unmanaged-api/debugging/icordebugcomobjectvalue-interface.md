---
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
ms.openlocfilehash: 528db447df4d71d67441b05ad29e6a900c59afbb
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892824"
---
# <a name="icordebugcomobjectvalue-interface"></a>Интерфейс ICorDebugComObjectValue Interface
Предоставляет методы для получения сведений, связанных с вызываемой оболочкой времени выполнения (RCW).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetCachedInterfacePointers](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|Возвращает необработанные указатели интерфейса, кэшированные в текущей RCW.|  
|[Метод GetCachedInterfaceTypes](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|Предоставляет перечислитель для типов интерфейса, к которым был применен регистр текущего объекта или использован в качестве.|  
  
## <a name="remarks"></a>Remarks  
 Чтобы проверить, представляет ли экземпляр интерфейса "ICorDebugValue" RCW, отладчик вызывает метод `QueryInterface` "ICorDebugValue" с. `IID_ICorDebugComObjectValue`  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
