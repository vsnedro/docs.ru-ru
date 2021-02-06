---
description: 'Дополнительные сведения о: <add> Element для <listeners> for <trace>'
title: <add> Элемент для <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: ffc0823e0c0ce1dcd9d9f19853929496b3248177
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639787"
---
# <a name="add-element-for-listeners-for-trace"></a>\<add> Элемент для \<listeners> для \<trace>

Добавляет прослушиватель в коллекцию **Listeners** .  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a>Синтаксис  
  
```xml  
<add name="name"
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**type**|Обязательный атрибут.<br /><br /> Указывает тип прослушивателя. Необходимо использовать строку, которая соответствует требованиям, указанным в указании [полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Необязательный атрибут.<br /><br /> Строка, передаваемая конструктору для указанного класса.|  
|**name**|Необязательный атрибут.<br /><br /> Указывает имя прослушивателя.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|Добавляет фильтр в прослушиватель в `Listeners` коллекции для трассировки.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`listeners`|Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения. Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.|  
|`system.diagnostics`|Задает корневой элемент для раздела конфигурации ASP.NET.|  
|`trace`|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
  
## <a name="remarks"></a>Remarks  

 <xref:System.Diagnostics.Debug>Классы и <xref:System.Diagnostics.Trace> совместно используют одну и ту же коллекцию **Listeners** . При добавлении объекта прослушивателя в коллекцию в одном из этих классов другой класс использует тот же прослушиватель. Классы прослушивателей являются производными от <xref:System.Diagnostics.TraceListener> .  
  
 Если `name` атрибут прослушивателя трассировки не указан, то <xref:System.Diagnostics.TraceListener.Name%2A> для прослушивателя трассировки по умолчанию используется пустая строка (""). Если у приложения есть только один прослушиватель, можно добавить его без указания имени и удалить его, указав в качестве имени пустую строку. Однако если приложение имеет более одного прослушивателя, необходимо указать уникальные имена для каждого прослушивателя трассировки, что позволяет определять отдельные прослушиватели трассировки в <xref:System.Diagnostics.Debug.Listeners%2A> коллекциях и управлять ими <xref:System.Diagnostics.Trace.Listeners%2A> .  
  
> [!NOTE]
> Добавление нескольких прослушивателей трассировки одного и того же типа и с одним и тем же именем приводит к тому, что только один прослушиватель трассировки этого типа и имя добавляются в `Listeners` коллекцию. Тем не менее можно программно добавить несколько идентичных прослушивателей в `Listeners` коллекцию.  
  
 Значение атрибута **initializeData** зависит от типа создаваемого прослушивателя. Не все прослушиватели трассировки нуждаются в указании **initializeData**.  
  
> [!NOTE]
> При использовании `initializeData` атрибута может появиться предупреждение компилятора "атрибут initializeData не объявлен". Это предупреждение возникает из-за того, что параметры конфигурации проверяются по абстрактному базовому классу <xref:System.Diagnostics.TraceListener> , который не распознает `initializeData` атрибут. Как правило, это предупреждение можно игнорировать для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.  
  
 В следующей таблице показаны прослушиватели трассировки, которые включены в платформа .NET Framework и описаны значения их атрибутов **initializeData** .  
  
|Класс прослушивателя трассировки|значение атрибута initializeData|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|`useErrorStream`Значение для <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктора.  Задайте для `initializeData` атрибута значение " `true` ", чтобы записывать выходные данные трассировки и отладки в <xref:System.Console.Error%2A?displayProperty=nameWithType> ; " `false` " для записи <xref:System.Console.Out%2A?displayProperty=nameWithType> .|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.DelimitedListTraceListener>.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|Имя существующего источника журнала событий.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.EventSchemaTraceListener> в который производится запись.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.TextWriterTraceListener> в который производится запись.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|Имя файла, <xref:System.Diagnostics.XmlWriterTraceListener> в который производится запись.|  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как использовать **\<add>** элементы для добавления прослушивателей `MyListener` и `MyEventListener` в коллекцию **Listeners** . `MyListener` создает файл с именем `MyListener.log` и записывает выходные данные в файл. `MyEventListener` создает запись в журнале событий.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [Схема параметров трассировки и отладки](index.md)
- [Прослушиватели трассировки](../../../debug-trace-profile/trace-listeners.md)
