---
title: Служебные контексты, доступные для расширений разметки и преобразователей типов
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], type converter services how-to
ms.assetid: b4dad00f-03da-4579-a4e9-d8d72d2ccbce
ms.openlocfilehash: 59c4385eb4df8c622be6164cdb0a1a911c445ca8
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432896"
---
# <a name="service-contexts-available-to-type-converters-and-markup-extensions"></a>Служебные контексты, доступные для расширений разметки и преобразователей типов
Авторам типов, поддерживающих использование преобразователей типов и расширений разметки, часто необходимы контекстные сведения о расположении использования в разметке или в окружающей структуре графа объектов. Сведения могут понадобиться, чтобы правильно создать экземпляр предоставленного объекта или чтобы объект ссылался на существующие объекты в графе объектов. При использовании служб Ысипотов .NET XAML контекст, который может потребоваться, разоблачается как ряд интерфейсов служб. Код поддержки преобразователей типов или разметки расширения может запросить службу, используя контекст поставщика службы, доступный и переданный из <xref:System.Xaml.XamlObjectWriter> или связанных типов. Контекст схемы XAML доступен напрямую через одну такую службу. В этом разделе описывается порядок доступа к контексту службы из реализации преобразователя значений и указывается список доступных служб и их роли.

## <a name="obtaining-services"></a>Получение служб

При реализации преобразователя значений часто требуется доступ к определенному контексту, в котором он применяется. Этот контекст может включать информацию, такую как активный контекст схемы XAML, доступ к системе отображения типов, которую предоставляют контекст схемы XAML и автор объектов XAML, и так далее. Службы, доступные для реализации расширения разметки или преобразователя типов, взаимодействуют с помощью параметров контекста, являющихся частью сигнатуры каждого виртуального метода. В каждом случае в контексте реализован класс <xref:System.IServiceProvider> , который может вызывать <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType> для запроса службы.

## <a name="services-for-a-markup-extension"></a>Службы для расширения разметки

<xref:System.Windows.Markup.MarkupExtension> содержит только один виртуальный метод <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>. Входной параметр `serviceProvider` определяет, как службы взаимодействуют с реализациями, когда расширение разметки вызывается обработчиком XAML. В следующем псевдокоде показано, как реализация расширения разметки может запросить службы в <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>:

```csharp
public override object ProvideValue(IServiceProvider serviceProvider)
{
...
    // Get the IXamlTypeResolver from the service provider
    if (serviceProvider == null)
    {
        throw new ArgumentNullException("serviceProvider");
    }
    IXamlTypeResolver xamlTypeResolver = serviceProvider.GetService(typeof(IXamlTypeResolver)) as IXamlTypeResolver;
    if (xamlTypeResolver == null)
   {
        throw new ArgumentException("IXamlTypeResolver"));
    }
...
}
```

## <a name="services-for-a-type-converter"></a>Службы для преобразователя типов

<xref:System.ComponentModel.TypeConverter> содержит четыре виртуальных метода, использующих контекст службы и поддерживающих использование XAML. Каждый из этих методов передает входной параметр `context` . Этот параметр имеет тип <xref:System.ComponentModel.ITypeDescriptorContext>, но интерфейс наследует <xref:System.IServiceProvider>, поэтому вам доступен метод <xref:System.IServiceProvider.GetService%2A> для реализации преобразователя типов.

В следующем псевдокоде показано, как реализация преобразователя типов для использований XAML может запросить службы в одном из переопределенных методов, в данном случае это <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>:

```csharp
public override object ConvertFrom(ITypeDescriptorContext typeDescriptorContext,
  CultureInfo cultureInfo,
  object source)
{
    IRootObjectProvider rootProvider = typeDescriptorContext.GetService(typeof(IRootObjectProvider)) as IRootObjectProvider;
    if (rootProvider != null && source is String)
    {
        //return something, else ...
    }
    throw GetConvertFromException(source);
}
```

## <a name="services-for-a-value-serializer"></a>Службы для сериализатора значений

Для контекста сериализатора значений используется тип поставщика службы, который относится к классу <xref:System.Windows.Markup.ValueSerializer> , <xref:System.Windows.Markup.IValueSerializerContext>. Этот контекст передается переопределениям четырех виртуальных методов <xref:System.Windows.Markup.ValueSerializer> . Вызовите <xref:System.IServiceProvider.GetService%2A> из контекста для получения служб.

## <a name="using-the-xaml-service-provider-contexts"></a>Использование контекстов поставщиков служб XAML

Поставщик услуг <xref:System.IServiceProvider.GetService%2A> для доступа к службам XAML, доступным для расширения разметки или преобразователей типа, реализуется как внутренний класс, с экспозицией только через интерфейс и тем, как он передается в соответствующий контекст. Всякий раз, когда операция обработки XAML в реализации по умолчанию .NET XAML Services пути нагрузки или сохранение пути вызывает соответствующие методы расширения разметки или преобразования типа, которые требуют контекста службы, этот внутренний объект передается. В зависимости от ситуации контекст системной службы предоставляет `MarkupExtensionContext` или `TextSyntaxContext`, но различия этих классов не имеют значения для разработчика. Вы взаимодействуете с ними, только запрашивая у них службы с помощью <xref:System.IServiceProvider.GetService%2A>.

## <a name="available-services-from-the-net-xaml-service-context"></a>Доступные услуги из контекста службы .NET XAML

Службы XAML .NET определяют службы для расширений разметки, преобразователей типов, сериализаторов значений и потенциально других обычаев. В следующих разделах описана каждая из этих служб и предоставлены рекомендации по их использованию в реализации.

### <a name="iserviceprovider"></a>IServiceProvider

**Справочная документация:**<xref:System.IServiceProvider>

**Отношение к:** Базовая эксплуатация инфраструктуры на основе службы <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType>в .NET, чтобы вы могли позвонить.

### <a name="itypedescriptorcontext"></a>ITypeDescriptorContext

**Справочная документация:**<xref:System.ComponentModel.ITypeDescriptorContext>

Происходит от <xref:System.IServiceProvider>. Этот класс представляет контекст в стандартных сигнатурах <xref:System.ComponentModel.TypeConverter> . <xref:System.ComponentModel.TypeConverter> — это класс, существовавший начиная с .NET Framework 1.0. Эта реализация предшествовала XAML и сценариям XAML <xref:System.ComponentModel.TypeConverter> для преобразования строковых типов. В контексте .NET XAML <xref:System.ComponentModel.TypeConverter> Services методы внедряются явно. Явная реализация указывает вызывающим объектам, что <xref:System.ComponentModel.ITypeDescriptorContext> API не связан с системами типов XAML, а также чтением или записью объектов в XAML. <xref:System.ComponentModel.ITypeDescriptorContext.Container%2A>, <xref:System.ComponentModel.ITypeDescriptorContext.Instance%2A>и, <xref:System.ComponentModel.ITypeDescriptorContext.PropertyDescriptor%2A> `null` как правило, возврат из контекста услуг .NET XAML.

### <a name="ivalueserializercontext"></a>IValueSerializerContext

**Справочная документация:**<xref:System.Windows.Markup.IValueSerializerContext>

Это производный от <xref:System.ComponentModel.ITypeDescriptorContext> класс, который также использует явные реализации для подавления ложных выводов о системе типов XAML. Поддерживает статические вспомогательные методы поиска в <xref:System.Windows.Markup.ValueSerializer>.

### <a name="ixamltyperesolver"></a>IXamlTypeResolver

**Справочная документация:**<xref:System.Windows.Markup.IXamlTypeResolver>

**Определено:** <xref:System.Windows.Markup> пространство имен, сборка System.Xaml  

**Область применения:** сценарии пути загрузки и взаимодействие с контекстом схемы языка XAML

**API службы:**  <xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A>

Может влиять на сопоставление типов XAML в CLR, необходимое, когда средство записи XAML создает объект среды CLR в графе объектов. <xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A> обрабатывает потенциально содержащую префикс строку, которая соответствует имени типа XAML (<xref:System.Xaml.XamlType.Name%2A?displayProperty=nameWithType>) и возвращает <xref:System.Type>среды CLR. Разрешение типов обычно сильно зависит от контекста схемы XAML. Только контекст схемы языка XAML учитывает, какие сборки загружаются и какие из них можно или нужно использовать для разрешения типов.

### <a name="iuricontext"></a>IUriContext

**Справочная документация:**<xref:System.Windows.Markup.IUriContext>

**Определено:** <xref:System.Windows.Markup> пространство имен, сборка System.Xaml  

**Область применения:** обработка пути загрузки и сохранения значений элементов, которые представляют собой URI или значения `x:Uri` .

**API службы:**  <xref:System.Windows.Markup.IUriContext.BaseUri%2A>

Эта служба сообщает глобально доступный корневой URI, если таковой имеется. Корневой URI можно использовать для разрешения относительных URI в абсолютные или наоборот. Этот сценарий, в основном, относится к службам приложений, предоставляемым конкретной платформой, или возможностям часто используемого класса корневого элемента в платформе. Базовый URI может быть установлен как параметр средства чтения XAML, который затем передается объекту средства записи XAML и предоставляется этой службой.

### <a name="iambientprovider"></a>IAmbientProvider

**Справочная документация:**<xref:System.Xaml.IAmbientProvider>

**Определено:** <xref:System.Xaml> пространство имен, сборка System.Xaml  

**Область применения:** обработки пути загрузки и задержка или оптимизация поиска типов.

**Сервисные AIS:**  <xref:System.Xaml.IAmbientProvider.GetAllAmbientValues%2A>, три других.

Понятие окружения в XAML — это метод пометки конкретного члена типа как внешнего. Или же тип может быть внешним, чтобы все значения свойств, хранящих экземпляр типа, считались внешними свойствами. Расширения разметки или преобразователи типов, находящиеся ниже вдоль потока узлов XAML и являющиеся потомками в графе объектов, могут получить доступ к внешнему свойству или экземпляру типа во время загрузки. Также они могут использовать знание внешней структуры, чтобы сэкономить время. Это может повлиять на степень определенности, необходимую для разрешения типов для других служб, таких как <xref:System.Windows.Markup.IXamlTypeResolver> или `x:Type`. Ознакомьтесь с командой <xref:System.Xaml.AmbientPropertyValue>.

### <a name="ixamlschemacontextprovider"></a>IXamlSchemaContextProvider

**Справочная документация:**<xref:System.Xaml.IXamlSchemaContextProvider>

**Определено:** <xref:System.Xaml> пространство имен, сборка System.Xaml  

**Область применения:** путь загрузки и любые операции, которым необходимо разрешить тип XAML в базовый тип.

**API службы:**  <xref:System.Xaml.IXamlSchemaContextProvider.SchemaContext%2A>

Контекст схемы XAML необходим для всех отложенных операций загрузки, так как этот же контекст схемы должен применяться в отложенной области, чтобы интегрировать отложенное содержимое. Дополнительные сведения о роли контекста схемы XAML см. в разделе [XAML Services](../../../api/index.md).

### <a name="irootobjectprovider"></a>IRootObjectProvider

**Справочная документация:**<xref:System.Xaml.IRootObjectProvider>

**Определено:** <xref:System.Xaml> пространство имен, сборка System.Xaml  

**Область применения:** путь загрузки.

**API службы:**  <xref:System.Xaml.IRootObjectProvider.RootObject%2A>

Эта служба относится к службам приложений, предоставляемым конкретной платформой, или возможностям часто используемого класса корневого элемента в платформе. Один из сценариев получения корневого объекта — подключение фонового кода и привязка событий. Например, реализация `x:Class` в WPF используется для компиляции разметки и привязки всех атрибутов обработчиков событий, находящихся в другом месте в разметке XAML. Точка подключения разметки и определенных в фоновом коде разделяемых классов для компиляции разметки находится в корневом элементе.

### <a name="ixamlnamespaceresolver"></a>IXamlNamespaceResolver

**Справочная документация:**<xref:System.Xaml.IXamlNamespaceResolver>

**Определено:** <xref:System.Xaml> пространство имен, сборка System.Xaml  

**Область применения:** путь загрузки, путь сохранения.

**API службы:** <xref:System.Xaml.IXamlNamespaceResolver.GetNamespace%2A> для пути загрузки, <xref:System.Xaml.IXamlNamespaceResolver.GetNamespacePrefixes%2A> для пути сохранения.

<xref:System.Xaml.IXamlNamespaceResolver> — это служба, которая может вернуть идентификатор или URI пространства имен XAML, используя его префикс, сопоставленный в исходной разметке XAML.

### <a name="iprovidevaluetarget"></a>IProvideValueTarget

**Справочная документация:**<xref:System.Windows.Markup.IProvideValueTarget>

**Определено:** <xref:System.Windows.Markup> пространство имен, сборка System.Xaml  

**Область применения:** путь загрузки, путь сохранения.

**Сервисные AIS:**<xref:System.Windows.Markup.IProvideValueTarget.TargetObject%2A>. <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A>  

<xref:System.Windows.Markup.IProvideValueTarget> позволяет преобразователям типов и расширениям разметки получать контекст расположения во время загрузки. Реализации могут применять этот контекст, чтобы сделать использование недействительным. Например, WPF располагает логикой внутри некоторых расширений разметки, таких как <xref:System.Windows.DynamicResourceExtension>. Эта логика проверяет <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A> , чтобы убедиться в том, что расширение используется только для задания свойств зависимостей (или краткого списка других свойств, не относящихся к зависимостям).

### <a name="ixamlnameresolver"></a>IXamlNameResolver

**Справочная документация:**<xref:System.Xaml.IXamlNameResolver>

**Определено:** <xref:System.Xaml> пространство имен, сборка System.Xaml  

**Отношение к:** Определение диаграммы объекта нагрузки, `x:Name` `x:Reference`разрешение объектов, идентифицированных, или методы, связанные с рамками.

**API службы:**  <xref:System.Xaml.IXamlNameResolver.Resolve%2A>; другие интерфейсы API для более сложных сценариев, таких как работа с прямыми ссылками.

Реализация обработки `x:Reference` .NET XAML опирается на эту услугу. Определенные платформы или средства, поддерживающие платформу, используют эту службу для обработки `x:Name` или эквивалентной обработки свойств (с атрибутами<xref:System.Windows.Markup.RuntimeNamePropertyAttribute> ).

### <a name="idestinationtypeprovider"></a>IDestinationTypeProvider

**Справочная документация:**<xref:System.Xaml.IDestinationTypeProvider>

**Определено:** <xref:System.Xaml> пространство имен, сборка System.Xaml  

**Область применения:** разрешение пути загрузки дополнительных сведений о типе CLR.

**API службы:** <xref:System.Xaml.IDestinationTypeProvider.GetDestinationType%2A>

Для получения дополнительной информации см. <xref:System.Xaml.IDestinationTypeProvider>.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Markup.MarkupExtension>
- <xref:System.Xaml.XamlObjectWriter>
- [Общие сведения о расширениях разметки для XAML](markup-extensions-overview.md)
- [Общие сведения о преобразователях типов для XAML](type-converters-overview.md)
