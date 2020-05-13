---
title: Интерфейс ICorDebugMergedAssemblyRecord
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 721f6c1cf468b3b518d2ea213588ae2410249690
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208724"
---
# <a name="icordebugmergedassemblyrecord-interface"></a>Интерфейс ICorDebugMergedAssemblyRecord
Предоставляет сведения о сборке после слияния.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetCulture](icordebugmergedassemblyrecord-getculture-method.md)|Возвращает строку с названием языка и региональных параметров сборки.|  
|[Метод GetIndex](icordebugmergedassemblyrecord-getindex-method.md)|Возвращает индекс префикса сборки.|  
|[Метод GetPublicKey](icordebugmergedassemblyrecord-getpublickey-method.md)|Возвращает открытый ключ сборки.|  
|[Метод GetPublicKeyToken](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|Возвращает токен открытого ключа сборки.|  
|[Метод GetSimpleName](icordebugmergedassemblyrecord-getsimplename-method.md)|Получает простое имя сборки.|  
|[Метод GetVersion](icordebugmergedassemblyrecord-getversion-method.md)|Возвращает сведения о версии сборки.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
