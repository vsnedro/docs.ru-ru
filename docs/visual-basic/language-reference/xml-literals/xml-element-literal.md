---
description: 'Дополнительные сведения: литерал XML-элемента (Visual Basic)'
title: XML-литерал элемента
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: dfc78beded5c6f472b67fa272835ef0aa29d0187
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787543"
---
# <a name="xml-element-literal-visual-basic"></a>Литеральное представление XML-элемента (Visual Basic)

Литерал, представляющий <xref:System.Xml.Linq.XElement> объект.

## <a name="syntax"></a>Синтаксис

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a>Компоненты

- `<`

  Обязательный элемент. Открывает начальный тег элемента.

- `name`

  Обязательный элемент. Имя элемента. Формат может быть одним из следующих:

  - Литеральный текст для имени элемента в форме `[ePrefix:]eName` , где:

    |Отделение|Описание|
    |---|---|
    |`ePrefix`|Необязательный элемент. Префикс пространства имен XML для элемента. Должно быть глобальным пространством имен XML, которое определено с помощью `Imports` инструкции в файле или на уровне проекта, или локального пространства имен XML, определенного в этом элементе или в родительском элементе.|
    |`eName`|Обязательный элемент. Имя элемента. Формат может быть одним из следующих:<br /><br /> — Литеральный текст. См. [Имена объявленных XML-элементов и атрибутов](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />— Внедренное выражение формы `<%= eNameExp %>` . Тип `eNameExp` должен быть `String` или типом, неявно преобразуемым в <xref:System.Xml.Linq.XName> .|

  - Внедренное выражение формы `<%= nameExp %>` . Тип `nameExp` должен быть `String` или типом, неявно преобразуемым в <xref:System.Xml.Linq.XName> . Внедренное выражение не допускается в закрывающем теге элемента.

- `attributeList`

  Необязательный элемент. Список атрибутов, объявленных в литерале.

  `attribute [ attribute ... ]`

  Каждый `attribute` из них имеет один из следующих синтаксисов:

  - Назначение атрибута в форме `[aPrefix:]aName=aValue` , где:

    |Отделение|Описание|
    |---|---|
    |`aPrefix`|Необязательный элемент. Префикс пространства имен XML для атрибута. Должно быть глобальным пространством имен XML, определенным `Imports` в операторе, или локальным пространством имен XML, которое определено в этом элементе или в родительском элементе.|
    |`aName`|Обязательный элемент. Имя атрибута. Формат может быть одним из следующих:<br /><br /> — Литеральный текст. См. [Имена объявленных XML-элементов и атрибутов](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />— Внедренное выражение формы `<%= aNameExp %>` . Тип `aNameExp` должен быть `String` или типом, неявно преобразуемым в <xref:System.Xml.Linq.XName> .|
    |`aValue`|Необязательный элемент. Значение атрибута. Формат может быть одним из следующих:<br /><br /> — Литеральный текст, заключенный в кавычки.<br />— Внедренное выражение формы `<%= aValueExp %>` . Разрешен любой тип.|

  - Внедренное выражение формы `<%= aExp %>` .

- `/>`

  Необязательный элемент. Указывает, что элемент является пустым элементом без содержимого.

- `>`

  Обязательный элемент. Завершает начальный или пустой тег элемента.

- `elementContents`

  Необязательный элемент. Содержимое элемента.

  `content [ content ... ]`

  Каждый `content` из них может быть одним из следующих:

  - Текст литерала. Все пробелы в `elementContents` значительной мере имеют литеральный текст.

  - Внедренное выражение формы `<%= contentExp %>` .

  - Литерал XML-элемента.

  - XML-литерал комментария. См. [XML-литерал комментария](xml-comment-literal.md).

  - Литерал инструкции обработки XML. См. раздел [XML-текст инструкции по обработке](xml-processing-instruction-literal.md).

  - XML-литерал CDATA. См. [XML CDATA Literal](xml-cdata-literal.md).

- `</[name]>`

  Необязательный элемент. Представляет закрывающий тег для элемента. Необязательный `name` параметр не допускается, если он является результатом внедренного выражения.

## <a name="return-value"></a>Возвращаемое значение

Объект <xref:System.Xml.Linq.XElement>.

## <a name="remarks"></a>Remarks

Для создания объектов в коде можно использовать синтаксис литерала XML-элемента <xref:System.Xml.Linq.XElement> .

> [!NOTE]
> XML-литерал может охватывать несколько строк без использования символов продолжения строки. Эта функция позволяет копировать содержимое из XML-документа и вставлять его непосредственно в Visual Basic программу.

Внедренные выражения формы `<%= exp %>` позволяют добавлять динамическую информацию в литерал XML-элемента. Дополнительные сведения см. [в разделе внедренные выражения в XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).

Компилятор Visual Basic преобразует литерал XML-элемента в вызовы <xref:System.Xml.Linq.XElement.%23ctor%2A> конструктора и, если это необходимо, <xref:System.Xml.Linq.XAttribute.%23ctor%2A> конструктор.

## <a name="xml-namespaces"></a>Пространства имен XML

Префиксы пространства имен XML полезны, когда необходимо создать XML-литералы с элементами из одного и того же пространства имен много раз в коде. Можно использовать глобальные префиксы пространства имен XML, которые определяются с помощью `Imports` инструкции или локальных префиксов, которые определяются с помощью `xmlns:xmlPrefix="xmlNamespace"` синтаксиса атрибута. Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../statements/imports-statement-xml-namespace.md).

В соответствии с правилами области для пространств имен XML локальные префиксы имеют приоритет над глобальными префиксами. Однако если XML-литерал определяет пространство имен XML, это пространство имен недоступно для выражений, которые отображаются во внедренном выражении. Внедренное выражение может обращаться только к глобальному пространству имен XML.

Компилятор Visual Basic преобразует каждое глобальное пространство имен XML, используемое XML-литералом, в одно локальное определение пространства имен в созданном коде. Глобальные пространства имен XML, которые не используются, не отображаются в созданном коде.

## <a name="example"></a>Пример

В следующем примере показано, как создать простой XML-элемент с двумя вложенными пустыми элементами.

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

В примере отображается следующий текст. Обратите внимание, что литерал сохраняет структуру пустых элементов.

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a>Пример

В следующем примере показано, как использовать внедренные выражения для именования элемента и создания атрибутов.

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

Этот пример кода отображает следующий текст:

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a>Пример

В следующем примере `ns` объявляется как префикс пространства имен XML. Затем он использует префикс пространства имен для создания XML-литерала и отображает окончательную форму элемента.

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

Этот пример кода отображает следующий текст:

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

Обратите внимание, что компилятор преобразует префикс глобального пространства имен XML в определение префикса для пространства имен XML. \<ns:middle>Элемент переопределяет префикс пространства имен XML для \<ns:inner1> элемента. Однако \<ns:inner2> элемент использует пространство имен, определенное `Imports` инструкцией.

## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement>
- [Имена объявленных элементов и атрибутов XML](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [XML-литерал комментария](xml-comment-literal.md)
- [XML-литерал CDATA](xml-cdata-literal.md)
- [XML-литералы](index.md)
- [Создание XML в Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Встроенные выражения в XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Оператор Imports (пространство имен XML)](../statements/imports-statement-xml-namespace.md)
