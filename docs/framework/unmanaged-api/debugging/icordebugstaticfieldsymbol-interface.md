---
description: 'Дополнительные сведения о: интерфейс Икордебугстатикфиелдсимбол'
title: Интерфейс ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: 3aa9c98cef4cdc7edc519b06b6cf9b4b2192b4e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794680"
---
# <a name="icordebugstaticfieldsymbol-interface"></a>Интерфейс ICorDebugStaticFieldSymbol

Представляет сведения символа отладки для статического поля.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetAddress](icordebugstaticfieldsymbol-getaddress-method.md)|Получает адрес статического поля.|  
|[Метод GetName](icordebugstaticfieldsymbol-getname-method.md)|Получает имя статического поля.|  
|[Метод GetSize](icordebugstaticfieldsymbol-getsize-method.md)|Получает размер статического поля в байтах.|  
  
## <a name="remarks"></a>Remarks  

 Интерфейс `ICorDebugStaticFieldSymbol` используется для извлечения сведений отладочного символа для статического поля.  
  
> [!NOTE]
> Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
