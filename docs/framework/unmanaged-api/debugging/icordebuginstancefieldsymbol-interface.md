---
description: 'Дополнительные сведения о: интерфейс ICorDebugInstanceFieldSymbol'
title: Интерфейс ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: aa47c858ec5b4b0d04b851357fe81c0fc9b2e30a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791137"
---
# <a name="icordebuginstancefieldsymbol-interface"></a>Интерфейс ICorDebugInstanceFieldSymbol

Представляет сведения отладочного символа для поля экземпляра.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetName](icordebuginstancefieldsymbol-getname-method.md)|Получает имя поля экземпляра.|  
|[Метод GetOffset](icordebuginstancefieldsymbol-getoffset-method.md)|Возвращает смещение в байтах этого поля экземпляра в его родительском классе.|  
|[Метод GetSize](icordebuginstancefieldsymbol-getsize-method.md)|Получает размер поля экземпляра в байтах.|  
  
## <a name="remarks"></a>Remarks  

 Интерфейс `ICorDebugInstanceFieldSymbol` используется для получения сведений символа отладки для поля экземпляра.  
  
> [!NOTE]
> Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
