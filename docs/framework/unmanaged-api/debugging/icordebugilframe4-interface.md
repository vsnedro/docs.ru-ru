---
title: Интерфейс ICorDebugILFrame4
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame4
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type:
- apiref
ms.openlocfilehash: d0b1c31d45efea4892182c43c801112530361994
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213706"
---
# <a name="icordebugilframe4-interface"></a>Интерфейс ICorDebugILFrame4
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Предоставляет методы, обеспечивающие доступ к локальным переменным и коду в кадре стека кода промежуточного языка. Параметр показывает, имеет ли отладчик доступ к переменным и коду, добавленным в инструментарий ReJIT профилировщика.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md)|Возвращает список локальных переменных, доступных в текущем кадре.|  
|[Метод GetCodeEx](icordebugilframe4-getcodeex-method.md)|Возвращает код, который выполняется этим кадром стека.|  
|[Метод GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md)|Возвращает значение локальной переменной в кадре промежуточного языка.|  
  
## <a name="remarks"></a>Remarks  
 Эти методы предоставляют функциональные возможности в дополнение к [возможностям,](icordebugframe-getcode-method.md)предоставляемым методами [енумерателокалвариаблес](icordebugilframe-enumeratelocalvariables-method.md), [жетлокалвариабле](icordebugilframe-getlocalvariable-method.md) и. Каждый метод включает параметр `flags`, определяющий видимость дополнительных локальных переменных или кода, определенных ReJIT-запросом профилировщика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
