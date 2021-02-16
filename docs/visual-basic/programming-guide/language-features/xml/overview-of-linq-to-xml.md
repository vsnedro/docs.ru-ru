---
description: Дополнительные сведения см. в статье Общие сведения о LINQ to XML в Visual Basic
title: Общие сведения о LINQ to XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: e70998706f62076a2528ac646df29e0c7081cb3d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480223"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Общие сведения о LINQ to XML в Visual Basic

Visual Basic обеспечивает поддержку [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] через литералы XML и свойства осей XML. Это позволяет использовать знакомый, удобный синтаксис для работы с XML в коде Visual Basic. *XML-литералы* позволяют включать XML непосредственно в код. *Свойства оси XML* позволяют получать доступ к дочерним узлам, узлам-потомкам и атрибутам XML. Дополнительные сведения см. в статьях [Общие сведения о XML-литералах](xml-literals-overview.md) и [доступ к XML в Visual Basic](accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] — API программирования XML в памяти, предназначенный специально для использования преимуществ Language-Integrated query (LINQ). Хотя интерфейсы API LINQ можно вызывать напрямую, только Visual Basic позволяет объявлять литералы XML и напрямую обращаться к свойствам осей XML.  
  
> [!NOTE]
> XML-литералы и свойства осей XML не поддерживаются в декларативном коде на странице ASP.NET. Чтобы использовать функции Visual Basic XML, разместите код на странице кода программной части в приложении ASP.NET.  
  
 [Кнопка "Воспроизвести"](./media/overview-of-linq-to-xml/play-video-icon-example.gif) Связанные демонстрационные видеоролики см [. в разделе как начать работу с LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) и [как создать электронные таблицы Excel с помощью LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml).
  
## <a name="creating-xml"></a>Создание XML  

 Существует два способа создания деревьев XML в Visual Basic. Вы можете объявить XML-литерал непосредственно в коде или использовать API LINQ для создания дерева. Оба процесса позволяют коду отражать окончательную структуру XML-дерева. Например, в следующем примере кода создается XML-элемент:  
  
 [!code-vb[VbXmlSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Дополнительные сведения см. [в разделе Создание XML в Visual Basic](creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Доступ и Навигация по XML  

 Visual Basic предоставляет свойства осей XML для доступа и навигации по XML-структурам. Эти свойства позволяют получить доступ к XML-элементам и атрибутам, указывая имена дочерних XML-элементов. Кроме того, можно явно вызвать методы LINQ для перемещения и поиска элементов и атрибутов. Например, в следующем примере кода свойства оси XML используются для ссылки на атрибуты и дочерние элементы XML-элемента. В примере кода используется запрос LINQ для получения дочерних элементов и их вывода в виде XML-элементов, фактически выполняющего преобразование.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Дополнительные сведения см. [в разделе доступ к XML в Visual Basic](accessing-xml.md).  
  
## <a name="xml-namespaces"></a>Пространства имен XML  

 Visual Basic позволяет указать псевдоним для глобального пространства имен XML с помощью `Imports` инструкции. В следующем примере показано, как использовать `Imports` инструкцию для импорта пространства имен XML:  
  
 [!code-vb[VbXMLSamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#1)]  
  
 При доступе к свойствам осей XML и объявлении XML-литералов для XML-документов и элементов можно использовать псевдоним пространства имен XML.  
  
 <xref:System.Xml.Linq.XNamespace>Объект для определенного префикса пространства имен можно получить с помощью [оператора GetXmlNamespace](../../../language-reference/operators/getxmlnamespace-operator.md).  
  
 Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Использование пространств имен XML в XML-литералах  

 В следующем примере показано, как создать <xref:System.Xml.Linq.XElement> объект, использующий глобальное пространство имен `ns` :  
  
 [!code-vb[VbXMLSamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#2)]  
  
 Компилятор Visual Basic преобразует литералы XML, содержащие псевдонимы пространства имен XML, в эквивалентный код, использующий XML-нотацию для использования пространств имен XML с `xmlns` атрибутом. При компиляции код в примере предыдущего раздела создает фактически тот же исполняемый код, что и в следующем примере:  
  
 [!code-vb[VbXMLSamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#3)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Использование пространств имен XML в свойствах оси XML  

 Пространства имен XML, объявленные в XML-литералах, недоступны для использования в свойствах осей XML. Однако глобальные пространства имен можно использовать со свойствами осей XML. Используйте двоеточие для отделения префикса пространства имен XML от имени локального элемента. Ниже приведен пример:  
  
 [!code-vb[VbXMLSamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#4)]  
  
## <a name="see-also"></a>См. также раздел

- [XML](index.md)
- [Создание XML в Visual Basic](creating-xml.md)
- [Доступ к XML в Visual Basic](accessing-xml.md)
- [Обработка XML в Visual Basic](manipulating-xml.md)
