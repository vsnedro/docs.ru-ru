---
description: 'Дополнительные сведения о: интерфейс IHostTaskManager'
title: Интерфейс IHostTaskManager
ms.date: 03/30/2017
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
ms.openlocfilehash: 67574550ba26970189ea53b8e6bdb867fea8549b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707488"
---
# <a name="ihosttaskmanager-interface"></a>Интерфейс IHostTaskManager

Предоставляет методы, позволяющие среде CLR работать с задачами через основное приложение, а не использовать стандартные функции потоков или волоконно-оптической операционной системы.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BeginDelayAbort](ihosttaskmanager-begindelayabort-method.md)|Уведомляет узел о том, что управляемый код вводит точку, в которой не нужно прерывать текущую задачу.|  
|[Метод BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md)|Уведомляет узел о том, что управляемый код вводит точку, в которой текущая задача не должна быть перемещена в другой поток операционной системы.|  
|[Метод CallNeedsHostHook](ihosttaskmanager-callneedshosthook-method.md)|Позволяет узлу указать, может ли среда CLR подставляемый вызов к неуправляемой функции.|  
|[Метод CreateTask](ihosttaskmanager-createtask-method.md)|Запрашивает создание новой задачи узлом.|  
|[Метод EndDelayAbort](ihosttaskmanager-enddelayabort-method.md)|Уведомляет узел о выходе управляемого кода за время, в течение которого текущая задача не должна прерываться, после предыдущего вызова `BeginDelayAbort` .|  
|[Метод EndThreadAffinity](ihosttaskmanager-endthreadaffinity-method.md)|Уведомляет узел о выходе управляемого кода за время, в течение которого текущая задача не должна быть перемещена в другой поток операционной системы, после предыдущего вызова `BeginThreadAffinity` .|  
|[Метод EnterRuntime](ihosttaskmanager-enterruntime-method.md)|Уведомляет узел о том, что вызов неуправляемого метода, например метода вызова платформы, возвращает управление выполнением в среду CLR.|  
|[Метод GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md)|Возвращает указатель интерфейса на задачу, которая выполняется в данный момент в потоке операционной системы, из которого выполняется этот вызов.|  
|[Метод GetStackGuarantee](ihosttaskmanager-getstackguarantee-method.md)|Возвращает объем стекового пространства, который гарантированно будет доступен после завершения операции с стеком, но до закрытия процесса.|  
|[Метод LeaveRuntime](ihosttaskmanager-leaveruntime-method.md)|Уведомляет узел о том, что управляемый код собирается выполнить вызов неуправляемой функции.|  
|[Метод ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md)|Уведомляет узел о том, что в среде CLR выполняется вызов из неуправляемого кода.|  
|[Метод ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md)|Уведомляет узел, что элемент управления выходит из среды CLR и вводит неуправляемую функцию, которая, в свою очередь, вызывается из управляемого кода.|  
|[Метод SetCLRTaskManager](ihosttaskmanager-setclrtaskmanager-method.md)|Предоставляет узлу указатель интерфейса на экземпляр [ICLRTaskManager](iclrtaskmanager-interface.md) , РЕАЛИЗУЕМый средой CLR.|  
|[Метод SetLocale](ihosttaskmanager-setlocale-method.md)|Уведомляет узел о том, что среда CLR изменила языковой стандарт текущей задачи.|  
|[Метод SetStackGuarantee](ihosttaskmanager-setstackguarantee-method.md)|Зарезервировано только для внутреннего использования.|  
|[Метод SetUILocale](ihosttaskmanager-setuilocale-method.md)|Уведомляет узел о том, что языковой стандарт пользовательского интерфейса был изменен в текущей задаче.|  
|[Метод Sleep](ihosttaskmanager-sleep-method.md)|Уведомляет узел о том, что текущая задача переходит в спящий режим.|  
|[Метод SwitchToTask](ihosttaskmanager-switchtotask-method.md)|Уведомляет узел о том, что необходимо отключить текущую задачу.|  
  
## <a name="remarks"></a>Remarks  

 `IHostTaskManager` позволяет среде CLR создавать задачи и управлять ими, чтобы обеспечить обработчики для узла на выполнение действий при передаче управления из управляемого кода в неуправляемый и наоборот, а также для указания определенных действий, которые узел может и не может принимать во время выполнения кода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRTask](iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](ihosttask-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
