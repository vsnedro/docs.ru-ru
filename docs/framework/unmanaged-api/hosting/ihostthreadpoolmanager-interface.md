---
description: 'Дополнительные сведения о: интерфейс IHostThreadPoolManager'
title: Интерфейс IHostThreadPoolManager
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
ms.openlocfilehash: 0361b7a08f781a8748e43959f65ce0e9f21bbac1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728423"
---
# <a name="ihostthreadpoolmanager-interface"></a>Интерфейс IHostThreadPoolManager

Предоставляет методы, позволяющие среде CLR настроить пул потоков и поместить рабочие элементы в очередь в пул потоков.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md)|Возвращает число потоков в пуле потоков, которые в данный момент не обрабатывают рабочие элементы.|  
|[Метод GetMaxThreads](ihostthreadpoolmanager-getmaxthreads-method.md)|Возвращает максимальное число потоков, которые обслуживается одновременно в пуле потоков.|  
|[Метод GetMinThreads](ihostthreadpoolmanager-getminthreads-method.md)|Возвращает минимальное число бездействующих потоков, поддерживаемых узлом в ожидаемых запросах.|  
|[Метод QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md)|Ставит в очередь функцию для выполнения и предоставляет объект, содержащий данные, которые будут использоваться функцией.|  
|[Метод SetMaxThreads](ihostthreadpoolmanager-setmaxthreads-method.md)|Задает максимальное число потоков, которые узел может поддерживать в пуле потоков.|  
|[Метод SetMinThreads](ihostthreadpoolmanager-setminthreads-method.md)|Задает минимальное число бездействующих потоков, которые должны поддерживаться узлом в ожидаемых запросах.|  
  
## <a name="remarks"></a>Remarks  

 Узел не требуется для настройки пула потоков с использованием значений, указанных в вызовах `SetMaxThreads` `SetMinThreads` методов и. В этом случае узел должен вернуть значение HRESULT E_NOTIMPL из этих методов.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [Интерфейсы размещения](hosting-interfaces.md)
