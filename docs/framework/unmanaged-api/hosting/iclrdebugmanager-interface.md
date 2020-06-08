---
title: Интерфейс ICLRDebugManager
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
ms.openlocfilehash: 653c8d1d3edd38e646b4e90c0e48dbe15bed102a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504268"
---
# <a name="iclrdebugmanager-interface"></a>Интерфейс ICLRDebugManager
Предоставляет методы, позволяющие узлу связать набор задач с идентификатором и понятным именем.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BeginConnection](iclrdebugmanager-beginconnection-method.md)|Устанавливает новое соединение между узлом и отладчиком для связывания задач с идентификатором и понятным именем.|  
|[Метод EndConnection](iclrdebugmanager-endconnection-method.md)|Удаляет связь между списком задач и идентификатором и понятным именем.|  
|[Метод GetDacl](iclrdebugmanager-getdacl-method.md)|Этот метод не реализован.|  
|[Метод IsDebuggerAttached](iclrdebugmanager-isdebuggerattached-method.md)|Получает значение, показывающее, присоединен ли отладчик к процессу.|  
|[Метод SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)|Связывает список экземпляров [ICLRTask](iclrtask-interface.md) с идентификатором и понятным именем.|  
|[Метод SetDacl](iclrdebugmanager-setdacl-method.md)|Этот метод не реализован.|  
|[Метод SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md)|Задает политику чтения файлов базы данных программы (PDB). Политика определяет, включаются ли в стеки вызовов сведения о номерах строк и файлах.|  
  
## <a name="remarks"></a>Примечания  
 В сценариях отладки узлу может потребоваться сгруппировать задачи в соответствии с собственной логикой программирования. Например, группирование позволит разработчику видеть только задачи, необходимые API разработчика, а не выполнять все задачи, выполняемые в процессе. `ICLRDebugManager`позволяет ведущему приложению реализовать такой тип группирования.  
  
> [!IMPORTANT]
> Три `ICLRDebugManager` метода, `BeginConnection` `SetConnectionTasks` и, `EndConnection` зависят друг от друга. Их необходимо вызывать в заданном порядке, чтобы работать должным образом.  
  
 Группирование и идентификаторы и понятные имена, которые узел назначает группе, не имеют смысла для среды CLR. CLR просто передает информацию в отладчик.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы размещения](hosting-interfaces.md)
