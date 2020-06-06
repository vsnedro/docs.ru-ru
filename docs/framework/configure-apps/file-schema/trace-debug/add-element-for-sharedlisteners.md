---
title: Элемент <add> для <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: 5588892ec75a791eda1eb043936c0af95e79354e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153611"
---
# <a name="add-element-for-sharedlisteners"></a>Элемент \<add> для \<sharedListeners>
Добавляет прослушиватель в коллекцию `sharedListeners`. `sharedListeners`— Это коллекция прослушивателей, [\<source>](source-element.md) на которые [\<trace>](trace-element.md) могут ссылаться любые или.  По умолчанию прослушиватели в `sharedListeners` коллекции не помещаются в `Listeners` коллекцию. Они должны быть добавлены по имени в [\<source>](source-element.md) или [\<trace>](trace-element.md) . Невозможно получить прослушиватели в `sharedListeners` коллекции в коде во время выполнения.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`name`|Обязательный атрибут.<br /><br /> Указывает имя прослушивателя, который используется для добавления общего прослушивателя в `Listeners` коллекцию.|  
|`type`|Обязательный атрибут.<br /><br /> Указывает тип прослушивателя. Необходимо использовать строку, которая соответствует требованиям, указанным в указании [полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`initializeData`|Необязательный атрибут.<br /><br /> Строка, передаваемая конструктору для указанного класса.|  
|`traceOutputOptions`|Необязательный атрибут.<br/><br/>Строковое представление одного или нескольких <xref:System.Diagnostics.TraceOptions> элементов перечисления, которое указывает данные, записываемые в выходные данные трассировки. Несколько элементов разделяются запятыми. Значение по умолчанию — None.|

### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|`sharedListeners`|Коллекция прослушивателей, на которые может ссылаться любой источник или элемент трассировки.|  
  
## <a name="remarks"></a>Примечания  
 Классы прослушивателей, поставляемые с .NET Framework, являются производными от <xref:System.Diagnostics.TraceListener> класса. Значение `name` атрибута используется для добавления общего прослушивателя в `Listeners` коллекцию либо для трассировки, либо для источника трассировки. Значение `initializeData` атрибута зависит от типа создаваемого прослушивателя. Не все прослушиватели трассировки нуждаются в указании `initializeData` .  
  
> [!NOTE]
> При использовании `initializeData` атрибута может появиться предупреждение компилятора "атрибут initializeData не объявлен". Это предупреждение возникает из-за того, что параметры конфигурации проверяются по абстрактному базовому классу <xref:System.Diagnostics.TraceListener> , который не распознает `initializeData` атрибут. Как правило, это предупреждение можно игнорировать для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.  
  
 В следующей таблице показаны прослушиватели трассировки, которые включены в состав .NET Framework и описываются значения их `initializeData` атрибутов.  
  
|Класс прослушивателя трассировки|значение атрибута initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|`useErrorStream`Значение для <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктора.  Задайте для `initializeData` атрибута значение " `true` ", чтобы записывать выходные данные трассировки и отладки в стандартный поток ошибок; задайте для него значение " `false` ", чтобы выполнить запись в стандартный выходной поток.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.EventSchemaTraceListener> в который производится запись.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.TextWriterTraceListener> в который производится запись.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|Имя файла, <xref:System.Diagnostics.XmlWriterTraceListener> в который производится запись.|  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `<add>` элементы для добавления в <xref:System.Diagnostics.TextWriterTraceListener> `textListener` `sharedListeners` коллекцию.   `textListener`добавляется по имени в `Listeners` коллекцию для источника трассировки `TraceSourceApp` . `textListener`Прослушиватель записывает выходные данные трассировки в файл myListener. log.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"
        type="System.Diagnostics.TextWriterTraceListener"
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [Схема параметров трассировки и отладки](index.md)
- [Прослушиватели трассировки](../../../debug-trace-profile/trace-listeners.md)
