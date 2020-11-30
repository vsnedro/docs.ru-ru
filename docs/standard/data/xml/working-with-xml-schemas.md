---
title: Работа с XML-схемами
ms.date: 03/30/2017
ms.assetid: bbbcc70c-bf9a-4f6a-af72-1bab5384a187
ms.openlocfilehash: 0290cd31d9477d2c5a30a6efa907263fed137258
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675494"
---
# <a name="working-with-xml-schemas"></a>Работа с XML-схемами

Чтобы определить структуру XML-документа, связи его элементов, типы данных, ограничения на содержимое, используется определение типа документа (DTD) или схема XSD. XML-документ имеет правильный формат, если он соответствует всем синтаксическим требованиям Рекомендации консорциума W3C по языку XML 1.0. Однако документ считается допустимым только в том случае, если он одновременно имеет правильный формат и соответствует ограничениям, заданным определением DTD или схемой. Следовательно, хотя все допустимые XML-документы имеют правильный формат, не все XML-документы правильного формата, являются допустимыми.  
  
 Дополнительные сведения о XML см. в [документации консорциума W3C по XML 1.0](https://www.w3.org/TR/REC-xml/). Для получения дополнительных сведений о XML-схеме см. документы [W3C XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/) (XML-схема W3C. Часть 1. Рекомендации по структурам) и [W3C XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/) (XML-схема W3C. Часть 1. Рекомендации по типам данных).  
  
## <a name="in-this-section"></a>В этом разделе  

 [Модель объектов схемы XML (SOM)](xml-schema-object-model-som.md)  
 Обсуждается модель SOM в пространстве имен <xref:System.Xml.Schema?displayProperty=nameWithType>, предоставляющем набор классов, который позволяет считывать схему XSD из файла или создавать ее в памяти программным образом.  
  
 [XmlSchemaSet для компиляции схемы](xmlschemaset-for-schema-compilation.md)  
 Обсуждается класс <xref:System.Xml.Schema.XmlSchemaSet>, представляющий собой кэш, где могут храниться и проверяться схемы XSD.  
  
 [Принудительная проверка с помощью XmlSchemaValidator](xmlschemavalidator-push-based-validation.md)  
 Обсуждается класс <xref:System.Xml.Schema.XmlSchemaValidator>, предоставляющий эффективный, высокопроизводительный механизм проверки XML-данных по схемам XSD в принудительном порядке.  
  
 [Выведение XML-схемы](inferring-an-xml-schema.md)  
 Обсуждается применение класса <xref:System.Xml.Schema.XmlSchemaInference> для выведения схемы XSD из структуры XML-документа.  
  
## <a name="reference"></a>Справочник  

 <xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader>  
  
## <a name="related-sections"></a>Связанные разделы  

 [Проверка XML-документа в модели DOM](validating-an-xml-document-in-the-dom.md)  
 Обсуждается проверка XML в модели DOM. XML можно проверять по мере загрузки в DOM, или проверять ранее не проверенный XML-документ в модели DOM.  
  
 [Проверка по схеме с помощью XPathNavigator](schema-validation-using-xpathnavigator.md)  
 Обсуждается проверка XML-документа, по которому производится перемещение и изменение с помощью класса <xref:System.Xml.XPath.XPathNavigator>.
