---
description: 'Дополнительные сведения о: интерфейс ICorDebugClass2'
title: Интерфейс ICorDebugClass2
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
ms.openlocfilehash: 80aa8e59ccc774141e7fcea130d1fc6a38fa37da
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711478"
---
# <a name="icordebugclass2-interface"></a>Интерфейс ICorDebugClass2

Представляет универсальный класс или класс параметром метода типа <xref:System.Type>. Этот интерфейс расширяет [ICorDebugClass](icordebugclass-interface.md).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetParameterizedType](icordebugclass2-getparameterizedtype-method.md)|Возвращает объявление типа для этого класса.|  
|[Метод SetJMCStatus](icordebugclass2-setjmcstatus-method.md)|Для каждого метода этого класса задает значение, указывающее, является ли метод определяемым пользователем кодом.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugClass](icordebugclass-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
