---
title: Элемент <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
ms.openlocfilehash: 69f15cc9583b397017ac30a0c567914495867c18
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153325"
---
# <a name="sharedlisteners-element"></a>Элемент \<sharedListeners>
Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.  По умолчанию эти прослушиватели не получают никаких трассировок, поэтому невозможно получить эти прослушиватели во время выполнения. Прослушиватели, идентифицированные как общие прослушиватели, можно добавлять в источники или трассировки по имени.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|Добавляет прослушиватель в коллекцию `sharedListeners`.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`Configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает корневой элемент для раздела конфигурации ASP.NET.|  
  
## <a name="remarks"></a>Примечания  
 Добавление прослушивателя в коллекцию общих прослушивателей не сделает его активным прослушивателем. Он по-прежнему должен быть добавлен в источник трассировки или в трассировку путем добавления в `Listeners` коллекцию для этого элемента Trace. Классы прослушивателей в .NET Framework являются производными от <xref:System.Diagnostics.TraceListener> класса.  
  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<sharedListeners>` элемент для добавления прослушивателя `console` в `Listeners` коллекцию для <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace> классов и. Прослушиватель трассировки консоли записывает данные трассировки в консоль с помощью вызовов либо к, либо к <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace> .  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.TraceListener>
- [Схема параметров трассировки и отладки](index.md)
- [Прослушиватели трассировки](../../../debug-trace-profile/trace-listeners.md)
