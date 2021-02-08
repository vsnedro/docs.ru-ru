---
description: Дополнительные сведения о перечислении Кордебугдекодивентфлагсвиндовс
title: Перечисление CorDebugDecodeEventFlagsWindows
ms.date: 03/30/2017
api_name:
- CorDebugDecodeEventFlagsWindows
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type:
- apiref
ms.openlocfilehash: 765ce4b967d00bd70becca666e2ed418614d6fe3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801700"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a>Перечисление CorDebugDecodeEventFlagsWindows

Предоставляет дополнительную информацию о событиях отладки на платформе Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|Указывает, что событие отладки является первичным исключением.|  
  
## <a name="remarks"></a>Remarks  

 Метод [ICorDebugProcess6::D екодивент](icordebugprocess6-decodeevent-method.md) включает `dwFlags` параметр, предоставляющий дополнительные сведения о событии отладки, значение которого зависит от целевой архитектуры. Перечисление `CorDebugDecodeEventFlagsWindows` можно использовать с событиями отладки на платформе Windows.  
  
> [!NOTE]
> Это перечисление предназначено для использования только в сценариях отладки .NET Native.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
