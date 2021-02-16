---
description: Дополнительные сведения см. в статье как преобразовать XML с помощью LINQ (Visual Basic).
title: Практическое руководство. Преобразование XML с помощью LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: 67e6f5f94cd71d960f742b660d3f223137bbd6d4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483642"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a>Практическое руководство. Преобразование XML с помощью LINQ (Visual Basic)

[XML-литералы](../../../language-reference/xml-literals/index.md) позволяют легко считывать XML-код из одного источника и преобразовывать его в новый формат XML. Можно использовать запросы LINQ для получения содержимого для преобразования или изменения содержимого существующего документа в новый формат XML.

Пример в этом разделе преобразует содержимое из исходного документа XML в HTML для просмотра в браузере.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

### <a name="to-transform-an-xml-document"></a>Преобразование XML-документа

1. В Visual Studio создайте новый проект Visual Basic в шаблоне проекта **консольное приложение** .

2. Дважды щелкните файл Module1. vb, созданный в проекте, чтобы изменить код Visual Basic. Добавьте следующий код в `Sub Main` `Module1` модуль. Этот код создает исходный XML-документ в виде <xref:System.Xml.Linq.XDocument> объекта.

    ```vb
    Dim catalog =
      <?xml version="1.0"?>
        <Catalog>
          <Book id="bk101">
            <Author>Garghentini, Davide</Author>
            <Title>XML Developer's Guide</Title>
            <Price>44.95</Price>
            <Description>
              An in-depth look at creating applications
              with <technology>XML</technology>. For
              <audience>beginners</audience> or
              <audience>advanced</audience> developers.
            </Description>
          </Book>
          <Book id="bk331">
            <Author>Spencer, Phil</Author>
            <Title>Developing Applications with Visual Basic .NET</Title>
            <Price>45.95</Price>
            <Description>
              Get the expert insights, practical code samples,
              and best practices you need
              to advance your expertise with <technology>Visual
              Basic .NET</technology>.
              Learn how to create faster, more reliable applications
              based on professional,
              pragmatic guidance by today's top <audience>developers</audience>.
            </Description>
          </Book>
        </Catalog>
    ```

     [Как загрузить XML из файла, строки или потока](how-to-load-xml-from-a-file-string-or-stream.md).

3. После создания исходного XML-документа добавьте следующий код, чтобы получить все \<Book> элементы из объекта и преобразовать их в HTML-документ. Список \<Book> элементов создается с помощью запроса LINQ, возвращающего коллекцию <xref:System.Xml.Linq.XElement> объектов, содержащих преобразованный HTML-код. Внедренные выражения можно использовать для размещения значений из исходного документа в новом XML-формате.

     Полученный HTML-документ записывается в файл с помощью <xref:System.Xml.Linq.XElement.Save%2A> метода.

    ```vb
    Dim htmlOutput =
      <html>
        <body>
          <%= From book In catalog.<Catalog>.<Book>
              Select <div>
                       <h1><%= book.<Title>.Value %></h1>
                       <h3><%= "By " & book.<Author>.Value %></h3>
                        <h3><%= "Price = " & book.<Price>.Value %></h3>
                        <h2>Description</h2>
                        <%= TransformDescription(book.<Description>(0)) %>
                        <hr/>
                      </div> %>
        </body>
      </html>

    htmlOutput.Save("BookDescription.html")
    ```

4. После `Sub Main` `Module1` добавьте новый метод ( `Sub` ) для преобразования \<Description> узла в указанный формат HTML. Этот метод вызывается кодом на предыдущем шаге и используется для сохранения формата \<Description> элементов.

     Этот метод заменяет вложенные элементы \<Description> элемента HTML. `ReplaceWith`Метод используется для сохранения расположения вложенных элементов. Преобразованное содержимое \<Description> элемента включается в элемент HTML-Абзац ( \<p> ). <xref:System.Xml.Linq.XContainer.Nodes%2A>Свойство используется для получения преобразованного содержимого \<Description> элемента. Это гарантирует, что вложенные элементы будут включены в преобразованное содержимое.

     Добавьте следующий код после `Sub Main` `Module1` .

    ```vb
    Public Function TransformDescription(ByVal desc As XElement) As XElement

      ' Replace <technology> elements with <b>.
      Dim content = (From element In desc...<technology>).ToList()

      If content.Count > 0 Then
        For i = 0 To content.Count - 1
          content(i).ReplaceWith(<b><%= content(i).Value %></b>)
        Next
      End If

      ' Replace <audience> elements with <i>.
      content = (From element In desc...<audience>).ToList()

      If content.Count > 0 Then
        For i = 0 To content.Count - 1
          content(i).ReplaceWith(<i><%= content(i).Value %></i>)
        Next
      End If

      ' Return the updated contents of the <Description> element.
      Return <p><%= desc.Nodes %></p>
    End Function
    ```

5. Сохраните изменения.

6. Нажмите клавишу F5, чтобы выполнить код. Полученный сохраненный документ будет выглядеть следующим образом:

    ```html
    <?xml version="1.0"?>
    <html>
      <body>
        <div>
          <h1>XML Developer's Guide</h1>
          <h3>By Garghentini, Davide</h3>
          <h3>Price = 44.95</h3>
          <h2>Description</h2>
          <p>
            An in-depth look at creating applications
            with <b>XML</b>. For
            <i>beginners</i> or
            <i>advanced</i> developers.
          </p>
          <hr />
        </div>
        <div>
          <h1>Developing Applications with Visual Basic .NET</h1>
          <h3>By Spencer, Phil</h3>
          <h3>Price = 45.95</h3>
          <h2>Description</h2>
          <p>
            Get the expert insights, practical code
            samples, and best practices you need
            to advance your expertise with <b>Visual
            Basic .NET</b>. Learn how to create faster,
            more reliable applications based on
            professional, pragmatic guidance by today's
            top <i>developers</i>.
          </p>
          <hr />
        </div>
      </body>
    </html>
    ```

## <a name="see-also"></a>См. также раздел

- [XML-литералы](../../../language-reference/xml-literals/index.md)
- [Обработка XML в Visual Basic](manipulating-xml.md)
- [XML](index.md)
- [Практическое руководство. Загрузка XML-кода из файла, строки или потока](how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../linq/index.md)
- [Introduction to LINQ in Visual Basic](../linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
