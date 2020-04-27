---
title: Сборка мусора .NET
ms.date: 04/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET Framework]
- memory, allocating
- common language runtime, garbage collection
- garbage collector
- cleanup operations
- garbage collection
- memory, releasing
- common language runtime, automatic memory management
- automatic memory management
- runtime, automatic memory management
- runtime, garbage collection
- garbage collection, about
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
ms.openlocfilehash: c087deb033a373dd8b3980feb7ec6901c7909569
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102246"
---
# <a name="garbage-collection"></a>Сборка мусора

Сборщик мусора .NET управляет выделением и освобождением памяти для приложения. При каждом создании объекта среда CLR выделяет память для объекта из управляемой кучи. Пока в управляемой куче есть доступное адресное пространство, среда выполнения продолжает выделять пространство для новых объектов. Тем не менее ресурсы памяти не безграничны. В конечном счете сборщику мусора необходимо выполнить сбор, чтобы освободить память. Механизм оптимизации сборщика мусора определяет наилучшее время для выполнения сбора, основываясь на выполненных операциях выделения памяти. Когда сборщик мусора выполняет сборку, он проверяет наличие объектов в управляемой куче, которые больше не используются приложением, а затем выполняет необходимые операции, чтобы освободить память.  
  
## <a name="in-this-section"></a>Содержание раздела
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Основы сборки мусора](../../../docs/standard/garbage-collection/fundamentals.md)|Описание работы сборки мусора, выделения объектов в управляемой куче и других базовых понятий.|  
|[Сборка мусора рабочей станции и сборка мусора сервера](workstation-server-gc.md)|Описывает различия между сборкой мусора рабочей станции для клиентских приложений и сборкой мусора сервера для серверных приложений.|
|[Фоновая сборка мусора](background-gc.md)|Описывает фоновую сборку мусора, которая представляет собой сборку объектов поколения 0 и 1 во время сборки объектов поколения 2.|
|[Куча больших объектов](large-object-heap.md)|Описывает кучу больших объектов (LOH) и то, как для них выполняется сборка мусора.|
|[Сборка мусора и производительность](../../../docs/standard/garbage-collection/performance.md)|Проверки производительности, которые можно использовать для диагностики проблем со сборкой мусора и производительностью.|  
|[Индуцированные коллекции](../../../docs/standard/garbage-collection/induced.md)|Описание выполнения сборки мусора.|  
|[Режимы задержки](../../../docs/standard/garbage-collection/latency.md)|Описание режимов, которые определяют степень вмешательства сборщика мусора.|  
|[Оптимизация совместного размещения веб-сайтов](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|Способы оптимизации сборки мусора на серверах, совместно используемыми небольшими веб-узлами.|  
|[Уведомления о сборке мусора](../../../docs/standard/garbage-collection/notifications.md)|Определение необходимости полной сборки мусора и времени завершения этой операции.|  
|[Отслеживание ресурсов домена приложения](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|Способы наблюдения за использованием ЦП и памяти доменом приложения.|  
|[Слабые ссылки](../../../docs/standard/garbage-collection/weak-references.md)|Описание функциональных возможностей, которые позволяют сборщику мусора обрабатывать объект, разрешая при этом приложению получать доступ к этому объекту.|  
  
## <a name="reference"></a>Справочник

- <xref:System.GC?displayProperty=nameWithType>  
- <xref:System.GCCollectionMode?displayProperty=nameWithType>  
- <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
- <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a>См. также

- [Очистка неуправляемых ресурсов](../../../docs/standard/garbage-collection/unmanaged.md)
