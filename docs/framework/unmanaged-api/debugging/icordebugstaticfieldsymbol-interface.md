---
title: Интерфейс ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: fcf3bb61ccd903f2dd375e638814247a98aaf7b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717569"
---
# <a name="icordebugstaticfieldsymbol-interface"></a>Интерфейс ICorDebugStaticFieldSymbol

Представляет сведения символа отладки для статического поля.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetAddress](icordebugstaticfieldsymbol-getaddress-method.md)|Получает адрес статического поля.|  
|[Метод GetName](icordebugstaticfieldsymbol-getname-method.md)|Получает имя статического поля.|  
|[Метод GetSize](icordebugstaticfieldsymbol-getsize-method.md)|Получает размер статического поля в байтах.|  
  
## <a name="remarks"></a>Комментарии  

 Интерфейс `ICorDebugStaticFieldSymbol` используется для извлечения сведений отладочного символа для статического поля.  
  
> [!NOTE]
> Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
