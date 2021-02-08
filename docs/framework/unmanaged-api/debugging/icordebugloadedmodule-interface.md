---
description: 'Дополнительные сведения о: интерфейс Икордебуглоадедмодуле'
title: Интерфейс ICorDebugLoadedModule
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
ms.openlocfilehash: 6a1b466a9d2d7781fad7ac2bc8c24f0b2a5c23e0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801232"
---
# <a name="icordebugloadedmodule-interface"></a>Интерфейс ICorDebugLoadedModule

Предоставляет сведения о загруженном модуле.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetBaseAddress](icordebugloadedmodule-getbaseaddress-method.md)|Получает базовый адрес загруженного модуля.|  
|[Метод GetName](icordebugloadedmodule-getname-method.md)|Получает имя загруженного модуля.|  
|[Метод GetSize](icordebugloadedmodule-getsize-method.md)|Возвращает размер в байтах загруженного модуля.|  
  
## <a name="remarks"></a>Remarks  

 Интерфейс `ICorDebugLoadedModule` реализуется с помощью отладчика и используется интерфейсами отладки среды CLR для получения сведений о загруженном модуле из отладчика.  
  
> [!NOTE]
> Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
