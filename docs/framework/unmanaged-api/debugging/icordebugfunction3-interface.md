---
title: Интерфейс ICorDebugFunction3
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: 8c9c507f00780d5ef5c5aeb28a1b10493351f37e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546976"
---
# <a name="icordebugfunction3-interface"></a>Интерфейс ICorDebugFunction3
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Логически расширяет интерфейс ICorDebugFunction для предоставления доступа к коду из запроса ReJIT.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetActiveReJitRequestILCode](icordebugfunction3-getactiverejitrequestilcode-method.md)|Возвращает указатель интерфейса на [икордебугилкоде](icordebugilcode-interface.md) , содержащий Il из активного запроса ReJIT.|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
- [ReJIT: руководство](/archive/blogs/davbr/rejit-a-how-to-guide)
