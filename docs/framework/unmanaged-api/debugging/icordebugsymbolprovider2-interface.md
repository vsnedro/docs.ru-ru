---
title: Интерфейс ICorDebugSymbolProvider2
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: e6712dca776bf4c20ce7fc8568e94399a81beecb
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379289"
---
# <a name="icordebugsymbolprovider2-interface"></a>Интерфейс ICorDebugSymbolProvider2
Логически расширяет интерфейс [метод icordebugsymbolprovider](icordebugsymbolprovider-interface.md) для получения дополнительных сведений об отладочных символах.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetFrameProps](icordebugsymbolprovider2-getframeprops-method.md)|Возвращает начальный относительный виртуальный адрес метода и родительского фрейма для указанного относительного виртуального адреса кода.|  
|[Метод GetGenericDictionaryInfo](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|Получает универсальную карту словаря|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
