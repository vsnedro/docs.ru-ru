---
title: Сериализация и метаданные
ms.date: 03/30/2017
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
ms.openlocfilehash: cc9adf0e6627ef3190e74fea5d4f0f3afd581811
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389220"
---
# <a name="serialization-and-metadata"></a>Сериализация и метаданные

Если ваше приложение сериализует и десериализует объекты, может потребоваться добавить записи в файл директив среды выполнения (. rd.xml) файл, чтобы гарантировать наличие необходимых метаданных во время выполнения. Существует две категории сериализаторов, и каждый требует различной обработки в файла директив среды выполнения:  
  
- Сериализиторы сторонних поставщиков на основе отражения. Они требуют изменений в файле директив среды выполнения и рассматриваются в следующем разделе.  
  
- Неотражающие сериализаторы, найденные в библиотеке класса .NET Framework. Они могут потребовать внесения изменений в файл директив среды выполнения и обсуждаются в разделе [Сериализаторы Майкрософт](#Microsoft).  
  
<a name="ThirdParty"></a>
## <a name="third-party-serializers"></a>Сериализаторы сторонних поставщиков

 Сериализаторы сторонних поставщиков, включая Newtonsoft.JSON, обычно основаны на отражении. Учитывая большой двоичный объект (BLOB) из сериализованных данных, поля данных назначаются конкретному типу путем поиска полей типа целевого объекта по имени. Как минимум, использование этих библиотек приводит к исключениям [MissingMetadataException](missingmetadataexception-class-net-native.md) для каждого объекта <xref:System.Type> при попытке сериализации или десериализации в коллекции `List<Type>`.  
  
 Самый простой способ решения проблем, вызванных отсутствующими метаданными для этих сериализаторов, состоит в сборе типов, которые будут использоваться при сериализации в одном пространстве имен (например, `App.Models`) и применить к нему директиву метаданных `Serialize`:  
  
```xml  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 Для получения информации о синтаксисе, используемом в примере, с [ \<>м.](namespace-element-net-native.md)  
  
<a name="Microsoft"></a>
## <a name="microsoft-serializers"></a>Сериализаторы Microsoft

 Несмотря на то, что классы <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> и <xref:System.Xml.Serialization.XmlSerializer> не рассчитывают на отражение, они требуют создания кода на основе объекта для сериализации или десериализации. Перегруженные конструкторы для каждого сериализатора содержа параметр <xref:System.Type>, который задает тип для сериализации или десериализации. Способ указания этого типа в коде определяет действие, которое необходимо выполнить, как описано в следующих двух разделах.  
  
### <a name="typeof-used-in-the-constructor"></a>TypeOf используется в конструкторе

 Если вы называете конструктора этих классов сериализации и включаете в вызов метода оператора [типофа,](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) **вам не нужно выполнять дополнительную работу.** Например, в каждом из следующих вызовов конструктора класса сериализации ключевое слово `typeof`используется как часть выражения, переданного в конструктор.  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 Компилятор .NET Native будет автоматически обрабатывать этот код.  
  
### <a name="typeof-used-outside-the-constructor"></a>TypeOf, использованный за пределами конструктора

 Если вы называете конструктора этих классов сериализации и используете оператора [типофа](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) Сз вне выражения, поставляемого на параметр конструктора, <xref:System.Type> как в следующем коде, компилятор .NET Native не может решить тип:  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 В этом случае необходимо указать тип в файле директив среды выполнения, добавив следующую запись:  
  
```xml  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 Аналогичным образом, если вы вызываете конструктора, <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29> <xref:System.Type> например, и предоставляете массив дополнительных объектов для сериализации, как в следующем коде, компилятор .NET Native не может решить эти типы.  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
Добавление записей, таких как следующие для каждого типа, в файл директив времени выполнения:  
  
```xml  
<Type Name="t" Browse="Required Public" />  
```  
  
Для получения информации о синтаксисе, используемом в примере, см [ \<>.](type-element-net-native.md)  
  
## <a name="see-also"></a>См. также

- [Ссылка на файл конфигурации директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Элементы директив среды выполнения](runtime-directive-elements.md)
- [\<Элемент типа>](type-element-net-native.md)
- [\<Названиепространства> Элемент](namespace-element-net-native.md)
