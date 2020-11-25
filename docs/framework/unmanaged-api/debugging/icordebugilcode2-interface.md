---
title: Интерфейс ICorDebugILCode2
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
ms.openlocfilehash: b9289b5afc88c926ce585a4e620364cf2dc979d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703334"
---
# <a name="icordebugilcode2-interface"></a>Интерфейс ICorDebugILCode2

[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Логически расширяет интерфейс [икордебугилкоде](icordebugilcode-interface.md) , чтобы предоставить методы, которые возвращают маркер для сигнатуры локальной переменной функции и сопоставляют смещенные промежуточные языки (IL) профилировщика с исходными смещениями Il метода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetInstrumentedILMap](icordebugilcode2-getinstrumentedilmap-method.md)|Возвращает сопоставление смещений инструментированного профилировщиком промежуточного языка со смещениями промежуточного языка исходного метода для этого экземпляра.|  
|[Метод GetLocalVarSigToken](icordebugilcode2-getlocalvarsigtoken-method.md)|Получает маркер метаданных для подписи локальной переменной, предназначенной для представленной этим экземпляром функции.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugILCode](icordebugilcode-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
