---
title: Ввод XmlDataDocument в XslTransform
ms.date: 03/30/2017
ms.assetid: a0b536b6-cdb3-4a44-86c2-3b2ebc7bd4c9
ms.openlocfilehash: 96ce5176b83a6dfcb9af29b55f4e5052915dba93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721950"
---
# <a name="xmldatadocument-input-to-xsltransform"></a>Ввод XmlDataDocument в XslTransform

> [!NOTE]
> Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0. Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. См. дополнительные сведения об [использовании класса XslCompiledTransform](using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](migrating-from-the-xsltransform-class.md).  
  
 Платформа Microsoft .NET Framework реализует модель DOM, чтобы предоставить доступ к данным в XML-документах и дополнительным классам для чтения, записи и перемещения в XML-документах. Класс <xref:System.Xml.XmlDataDocument> в пространстве имен <xref:System.Xml> обеспечивает реляционный доступ к данным с возможностью синхронизации с реляционными данными в объекте <xref:System.Data.DataSet>. Можно одновременно просматривать и управлять структурированными XML-документами через реляционное представление <xref:System.Data.DataSet> или управлять полуструктурированными XML-документами через представление модели DOM класса <xref:System.Xml.XmlDataDocument>. Поэтому класс <xref:System.Xml.XmlDataDocument> пересекает границы реляционной и XML-областей.  
  
 Если данные хранятся в реляционной структуре и нужно использовать их в качестве входных данных для XSLT-преобразования, можно загрузить реляционные данные в объект <xref:System.Data.DataSet> и связать их с объектом <xref:System.Xml.XmlDataDocument>. Объект <xref:System.Xml.XPath.XPathNavigator>, входной параметр для объекта <xref:System.Xml.Xsl.XslTransform>, реализован в классе <xref:System.Xml.XmlDataDocument> через интерфейс <xref:System.Xml.XPath.IXPathNavigable>. Принимая реляционные данные, загружая их в объект <xref:System.Data.DataSet> и используя синхронизацию в классе <xref:System.Xml.XmlDataDocument>, можно выполнить XSLT-преобразование реляционных данных.  
  
 Дополнительные сведения о применении преобразования реляционных данных см. в руководстве по [преобразованию XSLT в набор данных](../../../framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.XmlDataDocument>
- [Синхронизация DataSet и XmlDataDocument](../../../framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)
- [XSLT-преобразования с помощью класса XslTransform](xslt-transformations-with-the-xsltransform-class.md)
- [Реализация классом XslTransform XSLT-процессора](xsltransform-class-implements-the-xslt-processor.md)
- [XPathNavigator в преобразованиях](xpathnavigator-in-transformations.md)
- [XPathNodeIterator в преобразованиях](xpathnodeiterator-in-transformations.md)
- [Ввод XPathDocument в XslTransform](xpathdocument-input-to-xsltransform.md)
- [Ввод XmlDocument в XslTransform](xmldocument-input-to-xsltransform.md)
