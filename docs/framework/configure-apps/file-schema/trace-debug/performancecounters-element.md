---
description: 'Дополнительные сведения о: <performanceCounters> element'
title: Элемент <performanceCounters>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <performanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: 3a9a6c42575be3fc7fb5c5d80ffecd940894e164
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639579"
---
# <a name="performancecounters-element"></a>Элемент \<performanceCounters>

Задает размер глобальной памяти, совместно используемой счетчиками производительности.

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**  

## <a name="syntax"></a>Синтаксис

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|филемаппингсизе|Обязательный атрибут.<br /><br /> Он указывает размер глобальной памяти в байтах, используемой счетчиками производительности. Значение по умолчанию — 524288.|

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`Configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`system.diagnostics`|Задает корневой элемент для раздела конфигурации ASP.NET.|

## <a name="remarks"></a>Remarks

Для публикации данных производительности счетчики производительности используют размещенный в памяти файл или общую память.  Размер общей памяти определяет, сколько экземпляров можно использовать одновременно.  Существует два типа общей памяти: глобальная общая память и отдельная общая память.  Глобальная общая память используется всеми категориями счетчиков производительности, установленными с платформа .NET Framework версиями 1,0 или 1,1.  Категории счетчиков производительности, установленные с платформа .NET Framework версии 2,0, используют отдельную общую память, при этом каждая категория счетчиков производительности имеет собственную память.

Размер глобальной общей памяти можно задать только с помощью файла конфигурации.  Размер по умолчанию — 524 288 bДа, максимальный размер — 33 554 432 байт, а минимальный размер — 32 768 байт.  Так как глобальная общая память совместно используется всеми процессами и категориями, первый создатель определяет размер.  Если вы определяете размер в файле конфигурации приложения, этот размер используется только в том случае, если приложение является первым приложением, которое приводит к выполнению счетчиков производительности.  Следовательно, правильное расположение для указания `filemappingsize` значения — это файл Machine.config.  Отдельные счетчики производительности не могут освободить память в глобальной общей памяти, поэтому в конечном итоге исчерпана глобальная общая память, если создано большое количество экземпляров счетчиков производительности с разными именами.

Для размера отдельной общей памяти необходимо сначала указать значение DWORD Филемаппингсизе в разделе реестра HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\ *\<category name>* \перформанце, за которым следует значение, указанное для глобальной общей памяти в файле конфигурации. Если значение Филемаппингсизе не существует, то отдельный размер общей памяти устанавливается равным четвертому (1/4) глобальному параметру в файле конфигурации.

## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
