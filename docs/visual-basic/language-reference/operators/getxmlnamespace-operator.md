---
description: 'Дополнительные сведения о операторе: GetXmlNamespace (Visual Basic)'
title: Оператор GetXmlNamespace
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: 704ac22493a0d6ce1255d171ae3b418313b74f09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665917"
---
# <a name="getxmlnamespace-operator-visual-basic"></a>Оператор GetXmlNamespace (Visual Basic)

Возвращает <xref:System.Xml.Linq.XNamespace> объект, соответствующий указанному префиксу пространства имен XML.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>Компоненты  

 `xmlNamespacePrefix`  
 Необязательный элемент. Строка, определяющая префикс пространства имен XML. Если указано, эта строка должна быть допустимым идентификатором XML. Дополнительные сведения см. в разделе [Имена объявленных XML-элементов и атрибутов](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Если префикс не указан, возвращается пространство имен по умолчанию. Если пространство имен по умолчанию не указано, возвращается пустое пространство имен.  
  
## <a name="return-value"></a>Возвращаемое значение  

 <xref:System.Xml.Linq.XNamespace>Объект, соответствующий префиксу пространства имен XML.  
  
## <a name="remarks"></a>Remarks  

 `GetXmlNamespace`Оператор возвращает <xref:System.Xml.Linq.XNamespace> объект, соответствующий префиксу пространства имен XML `xmlNamespacePrefix` .  
  
 Префиксы пространства имен XML можно использовать непосредственно в XML-литералах и свойствах осей XML. Однако необходимо использовать `GetXmlNamespace` оператор для преобразования префикса пространства имен в <xref:System.Xml.Linq.XNamespace> объект, прежде чем его можно будет использовать в коде. К объекту можно добавить неполное имя элемента <xref:System.Xml.Linq.XNamespace> для получения полного <xref:System.Xml.Linq.XName> объекта, который [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] требуется многим методам.  
  
## <a name="example"></a>Пример  

 В следующем примере `ns` выполняется импорт в виде префикса пространства имен XML. Затем он использует префикс пространства имен для создания XML-литерала и доступа к первому дочернему узлу с полным именем `ns:phone` . Затем он передает этот дочерний узел в `ShowName` подпрограммы, которая конструирует полное имя с помощью `GetXmlNamespace` оператора. `ShowName`Затем подподпрограмма передает полное имя <xref:System.Xml.Linq.XNode.Ancestors%2A> методу, чтобы получить родительский `ns:contact` узел.  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 При вызове `TestGetXmlNamespace.RunSample()` отображается окно сообщения, содержащее следующий текст:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>См. также

- [Оператор Imports (пространство имен XML)](../statements/imports-statement-xml-namespace.md)
- [Доступ к XML в Visual Basic](../../programming-guide/language-features/xml/accessing-xml.md)
