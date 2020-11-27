---
title: Импорт и экспорт схемы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, schema import and export
- XsdDataContractExporter class
- XsdDataContractImporter class
ms.assetid: 0da32b50-ccd9-463a-844c-7fe803d3bf44
ms.openlocfilehash: 52a9e1bf4c9442bd42beb55b133a185c4a42148d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288571"
---
# <a name="schema-import-and-export"></a>Импорт и экспорт схемы

Windows Communication Foundation (WCF) включает новый механизм сериализации <xref:System.Runtime.Serialization.DataContractSerializer> . `DataContractSerializer`Преобразование между объектами .NET Framework и XML (в обоих направлениях). В дополнение к самому сериализатору, WCF включает связанные механизмы импорта схемы и экспорта схемы. *Схема* — это формальное, точное и понятное для компьютера описание формы XML, которую создает сериализатор или который десериализатор может получить. WCF использует язык определения схемы XML (XSD) консорциум W3C (W3C) в качестве представления схемы, который широко взаимодействует с несколькими сторонними платформами.  
  
 Компонент импорта схемы, <xref:System.Runtime.Serialization.XsdDataContractImporter> , принимает документ XSD-схемы и создает .NET Framework классы (обычно классы контрактов данных) таким образом, чтобы сериализованные формы соответствовали заданной схеме.  
  
 Например, следующий фрагмент схемы:  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
 создает следующий тип (он немного упрощен для удобства восприятия).  
  
 [!code-csharp[c_SchemaImportExport#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#1)]
 [!code-vb[c_SchemaImportExport#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#1)]  
  
 Обратите внимание, что созданный тип соответствует нескольким рекомендациям по контракту данных (см. рекомендации по [управлению версиями контракта данных](../best-practices-data-contract-versioning.md)):  
  
- Тип реализует интерфейс <xref:System.Runtime.Serialization.IExtensibleDataObject>. Дополнительные сведения о создании контрактов данных, обладающих прямой совместимостью, см. в разделе [Контракты данных, совместимые с любыми будущими изменениями](forward-compatible-data-contracts.md).  
  
- Данные-члены реализованы в виде открытых свойств, скрывающих закрытые поля.  
  
- Класс является разделяемым, и его можно дополнять без изменения уже созданного кода.  
  
 Класс <xref:System.Runtime.Serialization.XsdDataContractExporter> позволяет выполнять обратную операцию - принимать типы, сериализуемые с помощью `DataContractSerializer`, и создавать документ схемы XSD.  
  
## <a name="fidelity-is-not-guaranteed"></a>Совпадение не гарантируется  

 Нет гарантии, что при выполнении полного цикла преобразования схемы или типа будет обеспечено полное совпадение. ( *Цикл обработки* означает импорт схемы для создания набора классов и экспорт результата для повторного создания схемы.) Одна и та же схема не может быть возвращена. Обратный процесс также не гарантирует полного совпадения результатов. (Выполните экспорт типа для создания схемы и последующий импорт результата. Маловероятно, что будет получен такой же тип.)  
  
## <a name="supported-types"></a>Поддерживаемые типы  

 Модель контракта данных поддерживает только ограниченный набор элементов схемы, определенных консорциумом WC3. Если схема не соответствует этому ограниченному набору, во время импорта будет создано исключение. Например, не существует способа преобразовать член с данными контракта данных в атрибут XML. Таким образом, схемы, требующие использования атрибутов XML, не поддерживаются и вызывают появление исключений во время импорта, поскольку в этом случае невозможно создать контракт данных с правильным XML-представлением.  
  
 Например, следующий фрагмент схемы невозможно импортировать с использованием параметров импорта по умолчанию.  
  
 [!code-xml[c_SchemaImportExport#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#9)]  
  
 Дополнительные сведения см. в разделе [Справочник по схеме контракта данных](data-contract-schema-reference.md). Если схема не соответствует правилам контракта данных, следует использовать другой механизм сериализации. Например, класс <xref:System.Xml.Serialization.XmlSerializer> использует собственный механизм импорта схемы. Кроме того, имеется специальный режим импорта, где список поддерживаемых элементов схемы расширяется. Дополнительные сведения см. в разделе Создание <xref:System.Xml.Serialization.IXmlSerializable> типов в [импорте схемы для создания классов](importing-schema-to-generate-classes.md).  
  
 `XsdDataContractExporter`Поддерживает любые типы .NET Framework, которые могут быть сериализованы с помощью `DataContractSerializer` . Дополнительные сведения см. [в разделе Типы, поддерживаемые сериализатором контрактов данных](types-supported-by-the-data-contract-serializer.md). Обратите внимание, что схема, созданная с помощью класса `XsdDataContractExporter`, обычно содержит допустимые данные, которые могут использоваться классом `XsdDataContractImporter` (если только для изменения схемы не используется класс <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>).  
  
 Дополнительные сведения об использовании <xref:System.Runtime.Serialization.XsdDataContractImporter> см. в разделе [Импорт схемы для создания классов](importing-schema-to-generate-classes.md).  
  
 Дополнительные сведения об использовании см <xref:System.Runtime.Serialization.XsdDataContractExporter> . в разделе [Экспорт схем из классов](exporting-schemas-from-classes.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- <xref:System.Runtime.Serialization.XsdDataContractExporter>
- [Импорт схемы для создания классов](importing-schema-to-generate-classes.md)
- [Экспорт схем из классов](exporting-schemas-from-classes.md)
