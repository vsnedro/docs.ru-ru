---
description: 'Дополнительные сведения о: интерфейс ICorDebugMDA'
title: Интерфейс ICorDebugMDA
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
ms.openlocfilehash: 8e6e779c58d71b07edc9b63dff72aef728ebe050
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801129"
---
# <a name="icordebugmda-interface"></a>Интерфейс ICorDebugMDA

Представляет сообщение управляемого помощника по отладке (MDA).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetDescription](icordebugmda-getdescription-method.md)|Возвращает строку, содержащую описание этого MDA.|  
|[Метод GetFlags](icordebugmda-getflags-method.md)|Возвращает флаги, связанные с этим MDA.|  
|[Метод GetName](icordebugmda-getname-method.md)|Возвращает строку, содержащую имя этого MDA.|  
|[Метод GetOSThreadId](icordebugmda-getosthreadid-method.md)|Возвращает идентификатор потока операционной системы, в котором выполняется этот MDA.|  
|[Метод GetXML](icordebugmda-getxml-method.md)|Возвращает полный XML-поток, связанный с этим MDA.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Диагностика ошибок посредством управляемых помощников по отладке](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
