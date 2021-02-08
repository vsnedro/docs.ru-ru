---
description: Дополнительные сведения см. в статье Импорт схемы для создания классов.
title: Импорт схемы для создания классов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, schema import and export
- XsdDataContractImporter class
ms.assetid: b9170583-8c34-43bd-97bb-6c0c8dddeee0
ms.openlocfilehash: 787d2a40db6de8181c7e4d27df72fbc4ac032da2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802870"
---
# <a name="importing-schema-to-generate-classes"></a>Импорт схемы для создания классов

Чтобы создать классы из схем, которые можно использовать с Windows Communication Foundation (WCF), используйте <xref:System.Runtime.Serialization.XsdDataContractImporter> класс. В данном разделе описывается процесс и параметры импорта.  
  
## <a name="the-import-process"></a>Процесс импорта

 Процесс импорта схемы начинается с создания объекта <xref:System.Xml.Schema.XmlSchemaSet>, что приводит к созданию объекта <xref:System.CodeDom.CodeCompileUnit>.  
  
 `XmlSchemaSet`Компонент является частью модели объектов схемы (SOM) платформа .NET Framework, представляющей набор документов схемы языка определения схемы XML (XSD). Чтобы создать объект `XmlSchemaSet` из набора документов XSD, десериализуйте каждый документ в объект <xref:System.Xml.Schema.XmlSchema> (с помощью сериализатора <xref:System.Xml.Serialization.XmlSerializer>) и добавьте эти объекты в новый объект `XmlSchemaSet`.  
  
 `CodeCompileUnit`Является частью Code Document Object Model платформа .NET Framework (CodeDOM), который представляет платформа .NET Framework код абстрактным способом. Чтобы создать фактический код из `CodeCompileUnit`, используйте подкласс класса <xref:System.CodeDom.Compiler.CodeDomProvider>, например класс <xref:Microsoft.CSharp.CSharpCodeProvider> или класс <xref:Microsoft.VisualBasic.VBCodeProvider>.  
  
### <a name="to-import-a-schema"></a>Процедура импорта схемы  
  
1. Создайте экземпляр <xref:System.Runtime.Serialization.XsdDataContractImporter>.  
  
2. Необязательный элемент. Передайте объект `CodeCompileUnit` в конструктор. Типы, созданные во время импорта схемы, добавляются в этот экземпляр класса `CodeCompileUnit` вместо создания нового пустого экземпляра класса `CodeCompileUnit`.  
  
3. Необязательный элемент. Вызовите один из методов <xref:System.Runtime.Serialization.XsdDataContractImporter.CanImport%2A>. Метод определяет, является ли данная схема действительной схемой контракта данных и можно ли ее импортировать. Метод `CanImport` имеет те же перегрузки, что метод `Import` (см. следующий шаг).  
  
4. Вызовите один из перегруженных методов `Import`, например метод <xref:System.Runtime.Serialization.XsdDataContractImporter.Import%28System.Xml.Schema.XmlSchemaSet%29>.  
  
     Простейшая перегрузка принимает объект `XmlSchemaSet` и импортирует все типы, включая анонимные, найденные в данном наборе схем. Другие перегрузки позволяют указывать тип XSD или список типов для импорта (в виде объекта <xref:System.Xml.XmlQualifiedName> или коллекции объектов `XmlQualifiedName`). В этом случае импортируются только указанные типы. Перегрузка принимает объект <xref:System.Xml.Schema.XmlSchemaElement>, импортирующий определенный элемент из объекта `XmlSchemaSet` и его связанный тип (анонимный или нет). Эта перегрузка возвращает объект `XmlQualifiedName`, представляющий имя контракта данных типа, созданного для этого элемента.  
  
     При нескольких вызовах метода `Import` в один и тот же объект `CodeCompileUnit` добавляется несколько типов. Тип не создается в объекте `CodeCompileUnit` , если он уже имеется в нем. Вызовите метод `Import` несколько раз для одного и того же объекта `XsdDataContractImporter` вместо использования нескольких объектов `XsdDataContractImporter`. Этот метод рекомендуется использовать, чтобы избежать создания повторяющихся типов.  
  
    > [!NOTE]
    > В случае сбоя при импорте объект `CodeCompileUnit` будет находиться в непредсказуемом состоянии. Использование объекта `CodeCompileUnit`, возникшего после сбоя импорта, может привести к образованию уязвимых мест в системе безопасности.  
  
5. Для доступа к объекту `CodeCompileUnit` используется свойство <xref:System.Runtime.Serialization.XsdDataContractImporter.CodeCompileUnit%2A> .  
  
### <a name="import-options-customizing-the-generated-types"></a>Параметры импорта. Настройка созданных типов  

 Можно присвоить свойство <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> объекта <xref:System.Runtime.Serialization.XsdDataContractImporter> экземпляру класса <xref:System.Runtime.Serialization.ImportOptions> для управления различными аспектами процесса импорта. Некоторые параметры непосредственно влияют на созданные типы.  
  
#### <a name="controlling-the-access-level-generateinternal-or-the-internal-switch"></a>Управление уровнем доступа (GenerateInternal или коммутатор /internal)  

 Это соответствует параметру **/интернал** в [средстве служебной программы метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
 Как правило, открытые типы создаются из схемы с закрытыми полями и соответствующими свойствами открытых членов данных. Чтобы вместо этого создать внутренние типы, присвойте свойству <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A> значение `true`.  
  
 В следующем примере показана схема, преобразованная во внутренний класс после присвоения свойству <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A> значения `true.`  
  
 [!code-csharp[c_SchemaImportExport#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#2)]
 [!code-vb[c_SchemaImportExport#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#2)]  
  
#### <a name="controlling-namespaces-namespaces-or-the-namespace-switch"></a>Управление пространствами имен (Namespaces или коммутатор /namespace)  

 Это соответствует переключателю **/Namespace** в `Svcutil.exe` средстве.  
  
 Обычно типы, созданные из схемы, создаются в платформа .NET Framework пространствах имен, при этом каждое пространство имен XSD соответствует конкретному платформа .NET Framework пространству имен в соответствии с сопоставлением, описанным в [справочнике по схеме контракта данных](data-contract-schema-reference.md). Это сопоставление можно настроить, присвоив свойству <xref:System.Runtime.Serialization.ImportOptions.Namespaces%2A> значение <xref:System.Collections.Generic.Dictionary%602>. Если данное пространство имен XSD найдено в словаре, то соответствующее платформа .NET Frameworkое пространство имен также берется из словаря.  
  
 Например, рассмотрим следующую схему.  
  
 [!code-xml[c_SchemaImportExport#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#10)]  
  
 В следующем примере свойство используется `Namespaces` для того, чтобы связать `http://schemas.contoso.com/carSchema` пространство имен с contoso. автомобили.  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
#### <a name="adding-the-serializableattribute-generateserializable-or-the-serializable-switch"></a>Добавление SerializableAttribute (GenerateSerializable или коммутатор /serializable)  

 Это соответствует параметру **/сериализабле** в `Svcutil.exe` средстве.  
  
 Иногда важно, чтобы типы, формируемые из схемы, можно было использовать с механизмами сериализации среды выполнения платформа .NET Framework (например, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> классы и <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> ). Это полезно при использовании типов для удаленного взаимодействия платформа .NET Framework. Чтобы включить эту возможность, необходимо применить атрибут <xref:System.SerializableAttribute> к созданным типам помимо обычного атрибута <xref:System.Runtime.Serialization.DataContractAttribute>. Этот атрибут создается автоматически, если параметр импорта `GenerateSerializable` имеет значение `true`.  
  
 В следующем примере показан класс `Vehicle`, при создании которого параметр импорта `GenerateSerializable` был установлен на значение `true`.  
  
 [!code-csharp[c_SchemaImportExport#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#4)]
 [!code-vb[c_SchemaImportExport#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#4)]  
  
#### <a name="adding-data-binding-support-enabledatabinding-or-the-enabledatabinding-switch"></a>Добавление поддержки привязки данных (EnableDataBinding или коммутатор /enableDataBinding)  

 Это соответствует параметру **/енабледатабиндинг** в средстве Svcutil.exe.  
  
 Иногда возникает необходимость привязать созданные из схемы типы к компонентам графического пользовательского интерфейса, чтобы при каждом обновлении экземпляров этих типов автоматически обновлялся пользовательский интерфейс. Объект `XsdDataContractImporter` может создавать типы, реализующие интерфейс <xref:System.ComponentModel.INotifyPropertyChanged> способом, обеспечивающим вызов события при любом изменении свойства. При создании типов для использования в среде программирования пользовательского интерфейса клиента, поддерживающей этот интерфейс (например, Windows Presentation Foundation (WPF)), задайте для <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> свойства значение `true` , чтобы включить эту функцию.  
  
 В следующем примере показан класс `Vehicle`, при создании которого параметр импорта <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> был установлен на значение `true`.  
  
 [!code-csharp[C_SchemaImportExport#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#5)]
 [!code-vb[C_SchemaImportExport#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#5)]  
  
### <a name="import-options-choosing-collection-types"></a>Параметры импорта. Выбор типов коллекции  

 Коллекции элементов представляют два специальных шаблона в формате XML: список элементов и ассоциации между двумя элементами. Ниже представлен пример списка строк.  
  
 [!code-xml[C_SchemaImportExport#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#11)]  
  
 Ниже приведен пример ассоциации между строкой и целым числом (`city name` и `population`).  
  
 [!code-xml[C_SchemaImportExport#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#12)]  
  
> [!NOTE]
> Любая ассоциация может также считаться списком. Например, указанную выше ассоциацию можно рассматривать как список сложных объектов `city` с двумя полями (полем строки и целочисленным полем). Оба шаблона имеют представление в схеме XSD. Не существует способа различать список и ассоциацию, поэтому такие закономерности всегда обрабатываются как списки, если в схеме нет особой аннотации, относящейся к WCF. В заметке указывается, что данный шаблон представляет ассоциацию. Дополнительные сведения см. в разделе [Справочник по схеме контракта данных](data-contract-schema-reference.md).  
  
 Обычно список импортируется как контракт данных коллекции, производный от универсального списка, или как массив платформа .NET Framework, в зависимости от того, соответствует ли схема стандартному шаблону именования для коллекций. Это более подробно описано в разделе [типы коллекций в контрактах данных](collection-types-in-data-contracts.md). Обычно ассоциации импортируются либо в виде <xref:System.Collections.Generic.Dictionary%602>, либо в виде контракта данных коллекции, наследуемого от объекта словаря. Например, рассмотрим следующую схему.  
  
 [!code-xml[c_SchemaImportExport#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#13)]  
  
 Импорт выполняется следующим образом (вместо свойств для удобочитаемости показаны поля.)  
  
 [!code-csharp[c_SchemaImportExport#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#6)]
 [!code-vb[c_SchemaImportExport#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#6)]  
  
 Можно настроить типы коллекций, созданные для таких шаблонов схемы. Например, может потребоваться создать коллекции, наследуемые от класса <xref:System.ComponentModel.BindingList%601>, а не от класса <xref:System.Collections.Generic.List%601>, для привязки типа к списку и его автоматического обновления при изменении содержимого коллекции. Для этого присвойте свойство <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> класса <xref:System.Runtime.Serialization.ImportOptions> списку типов коллекций, которые должны использоваться (в дальнейшем называемых "ссылочные типы"). При импорте какой-либо коллекции выполняется сканирование этого списка ссылочных типов коллекций и используется наиболее подходящая коллекция, если таковая найдена. Ассоциации сопоставляются только с типами, реализующими универсальный или неуниверсальный интерфейс <xref:System.Collections.IDictionary>, в то время как списки сопоставляются с любым поддерживаемым типом коллекции.  
  
 Например, если свойству <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> присвоено значение <xref:System.ComponentModel.BindingList%601>, тип `people` в предыдущем примере создается следующим образом.  
  
 [!code-csharp[C_SchemaImportExport#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#7)]
 [!code-vb[C_SchemaImportExport#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#7)]  
  
 Закрытый универсальный интерфейс считается наиболее подходящим. Например, если типы `BindingList(Of Integer)` и <xref:System.Collections.ArrayList> передаются в коллекцию ссылочных типов, любые списки целых чисел, найденные в схеме, импортируются как `BindingList(Of Integer)`. Любые другие списки, например `List(Of String)`, импортируются как `ArrayList`.  
  
 Если тип, реализующий универсальный интерфейс `IDictionary`, добавляется в коллекцию ссылочных типов, параметры этого типа должны быть либо полностью открытыми, либо полностью закрытыми.  
  
 Дубликаты не разрешены. Например, нельзя добавить и `List(Of Integer)`, и `Collection(Of Integer)` в ссылочные типы. Это делает невозможным определение типа, который следует использовать при обнаружении списка целых чисел в схеме. Дубликаты обнаруживаются, только если в схеме есть тип, указывающий на проблему дубликатов. Например, если импортируемая схема не содержит список целых чисел, допускается иметь оба типа: `List(Of Integer)` и `Collection(Of Integer)` в коллекции ссылочных типов, но ни тот, ни другой не будут действовать.  
  
 Механизм ссылочных типов коллекций работает одинаково хорошо как для коллекций сложных типов (включая коллекции других коллекций), так и для коллекций примитивов.  
  
 `ReferencedCollectionTypes`Свойство соответствует параметру **/коллектионтипе** в средстве SvcUtil.exe. Обратите внимание, что для ссылки на несколько типов коллекций параметр **/коллектионтипе** должен быть указан несколько раз. Если тип не находится в MsCorLib.dll, его сборку также необходимо ссылаться с помощью параметра **/Reference** .  
  
#### <a name="import-options-referencing-existing-types"></a>Параметры импорта. Ссылка на существующие типы  

 Иногда типы в схеме соответствуют существующим типам платформа .NET Framework, и нет необходимости создавать эти типы с нуля. (Сведения, представленные в данном разделе, применимы только к типам, не являющимся коллекциями. Дополнительные сведения о типах коллекций см. в предыдущем разделе.)  
  
 Например, имеется стандартный корпоративный тип контракта данных "Person", который всегда необходимо использовать при представлении лица. Всякий раз при использовании этого типа некоторыми службами и при отображении его схемы в метаданных службы может возникать необходимость в повторном использовании существующего типа `Person` при импорте этой схемы вместо создания нового типа для каждой службы.  
  
 Для этого передайте список типов платформа .NET Framework, которые вы хотите повторно использовать, в коллекцию, <xref:System.Runtime.Serialization.ImportOptions.ReferencedTypes%2A> возвращаемую свойством в <xref:System.Runtime.Serialization.ImportOptions> классе. Если какой-либо из этих типов имеет имя контракта данных и пространство имен, соответствующие имени и пространству имен типа схемы, выполняется структурное сравнение. Если определено, что типы имеют как совпадающие имена, так и совпадающие структуры, существующий тип платформа .NET Framework используется повторно вместо создания нового. Если соответствует только имя, но не структура, вызывается исключение. Обратите внимание, при создании ссылок на типы управление версиями не допускается (например, добавление новых необязательных членов данных). Структуры должны совпадать полностью.  
  
 Допустимо добавлять несколько типов с одинаковым именем контракта данных и пространством имен в коллекцию ссылочных типов, если никакие типы схемы не импортируются с этим именем и пространством имен. Это позволит быстро добавлять все типы в сборке в коллекцию, не задумываясь о возможных проблемах с дубликатами для типов, которые в настоящий момент отсутствуют в схеме.  
  
 `ReferencedTypes`Свойство соответствует параметру **/Reference** в определенных режимах работы средства Svcutil.exe.  
  
> [!NOTE]
> При использовании Svcutil.exe или (в Visual Studio) средств **Добавление ссылки на службу** все типы в MsCorLib.dll автоматически упоминаются.  
  
#### <a name="import-options-importing-non-datacontract-schema-as-ixmlserializable-types"></a>Параметры импорта. Импорт схемы, отличной от DataContract, в виде типов IXmlSerializable  

 Объект <xref:System.Runtime.Serialization.XsdDataContractImporter> поддерживает ограниченное подмножество схемы. При наличии неподдерживаемых конструкций схемы (например, атрибутов XML) попытка импорта заканчивается с ошибкой, и возникает исключение. Однако, если присвоить свойству <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> значение `true`, диапазон поддерживаемых схем увеличится. При выборе значения `true` объект <xref:System.Runtime.Serialization.XsdDataContractImporter> создает типы, реализующие интерфейс <xref:System.Xml.Serialization.IXmlSerializable>. Это обеспечивает прямой доступ к XML-представлению этих типов.  
  
##### <a name="design-considerations"></a>Вопросы проектирования  
  
- Возможно, будет трудно работать со слабо типизированным XML-представлением напрямую. При работе со схемой, не совместимой с контрактами данных строго типизированным способом, рекомендуется использовать альтернативный модуль сериализации, такой как <xref:System.Xml.Serialization.XmlSerializer>. Дополнительные сведения см. [в разделе Использование класса XmlSerializer](using-the-xmlserializer-class.md).  
  
- Некоторые конструкции схемы невозможно импортировать с помощью <xref:System.Runtime.Serialization.XsdDataContractImporter>, даже если свойству <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> присвоено значение `true`. В таких случаях также рекомендуется использовать <xref:System.Xml.Serialization.XmlSerializer>.  
  
- Точные конструкции схемы, которые поддерживаются, если <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> имеет значение `true` или `false` описаны в [справочнике по схеме контракта данных](data-contract-schema-reference.md).  
  
- При импорте и экспорте точность схемы для созданных типов <xref:System.Xml.Serialization.IXmlSerializable> не сохраняется. Это значит, что при экспорте схемы из созданных типов и импорте в виде классов исходная схема не возвращается.  
  
 Можно сгруппировать параметр <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> и параметр <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A>, описанные выше. В случае типов, которые необходимо создать как реализации <xref:System.Xml.Serialization.IXmlSerializable>, структурная проверка пропускается при использовании возможности <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A>.  
  
 <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A>Параметр соответствует переключателю **/импортксмлтипес** в средстве Svcutil.exe.  
  
##### <a name="working-with-generated-ixmlserializable-types"></a>Работа с созданными типами IXmlSerializable  

 Созданные типы `IXmlSerializable` содержат закрытое поле с именем "nodesField", возвращающее массив объектов <xref:System.Xml.XmlNode>. При десериализации экземпляра такого типа доступ к данным XML можно получить непосредственно через это поле с помощью документной объектной модели XML. При сериализации экземпляра этого типа можно настроить это поле на требуемые данные XML, и он будет сериализован.  
  
 Это возможно благодаря реализации `IXmlSerializable`. В созданном типе `IXmlSerializable` реализация <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> вызывает метод <xref:System.Runtime.Serialization.XmlSerializableServices.ReadNodes%2A> класса <xref:System.Runtime.Serialization.XmlSerializableServices>. Этот метод является вспомогательным методом, преобразующим данные XML, предоставленные с помощью <xref:System.Xml.XmlReader>, в массив объектов <xref:System.Xml.XmlNode>. Реализация <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> выполняет противоположные действия и преобразовывает массив объектов `XmlNode` в последовательность вызовов <xref:System.Xml.XmlWriter>. Это возможно благодаря методу <xref:System.Runtime.Serialization.XmlSerializableServices.WriteNodes%2A>.  
  
 Процесс экспорта схемы можно выполнить в созданных классах `IXmlSerializable`. Как уже говорилось ранее, исходная схема не возвращается. Вместо этого будет получен стандартный тип XSD "anyType", который является подстановочным знаком для любого типа XSD.  
  
 Это достигается путем применения <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> атрибута к создаваемым `IXmlSerializable` классам и указания метода, который вызывает <xref:System.Runtime.Serialization.XmlSerializableServices.AddDefaultSchema%2A> метод для создания типа anyType.  
  
> [!NOTE]
> Тип <xref:System.Runtime.Serialization.XmlSerializableServices> существует только для поддержки этой конкретной функции. Не рекомендуется использовать его для других целей.  
  
#### <a name="import-options-advanced-options"></a>Параметры импорта. Дополнительные параметры  

 Ниже представлены дополнительные параметры импорта.  
  
- Свойство <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A>. Укажите класс <xref:System.CodeDom.Compiler.CodeDomProvider>, используемый для создания кода для созданных классов. Механизм импорта пытается избежать возможностей, не поддерживаемых классом <xref:System.CodeDom.Compiler.CodeDomProvider>. Если параметр <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A> не задан, используется полный набор платформа .NET Framework компонентов без ограничений.  
  
- Свойство <xref:System.Runtime.Serialization.ImportOptions.DataContractSurrogate%2A>. С помощью этого свойства можно указать реализацию <xref:System.Runtime.Serialization.IDataContractSurrogate>. В реализации <xref:System.Runtime.Serialization.IDataContractSurrogate> настраивается процесс импорта. Дополнительные сведения см. в разделе [суррогаты контракта данных](../extending/data-contract-surrogates.md). По умолчанию суррогат не используется.  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- <xref:System.Runtime.Serialization.XsdDataContractExporter>
- <xref:System.Runtime.Serialization.ImportOptions>
- [Справочник по схеме контрактов данных](data-contract-schema-reference.md)
- [Суррогаты контрактов данных](../extending/data-contract-surrogates.md)
- [Импорт и экспорт схемы](schema-import-and-export.md)
- [Экспорт схем из классов](exporting-schemas-from-classes.md)
- [Справочник по схеме контрактов данных](data-contract-schema-reference.md)
