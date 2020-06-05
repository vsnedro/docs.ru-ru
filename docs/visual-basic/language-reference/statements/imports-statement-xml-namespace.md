---
title: Оператор Imports — пространство имен XML
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: a3184d68b0e4cdff5d4296a5a638e22b4e83bcde
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404541"
---
# <a name="imports-statement-xml-namespace"></a>Оператор Imports (пространство имен XML)

Импортирует префиксы пространства имен XML для использования в XML-литералах и свойствах осей XML.

## <a name="syntax"></a>Синтаксис

```vb
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">
```

## <a name="parts"></a>Компоненты

`xmlNamespacePrefix`  
Необязательный элемент. Строка, с помощью которой можно ссылаться на элементы и атрибуты XML `xmlNamespaceName` . Если `xmlNamespacePrefix` аргумент не указан, импортированное пространство имен XML является пространством имен XML по умолчанию. Должен быть допустимым идентификатором XML. Дополнительные сведения см. в разделе [Имена объявленных XML-элементов и атрибутов](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).

`xmlNamespaceName`  
Обязательный. Строка, идентифицирующая импортируемое пространство имен XML.

## <a name="remarks"></a>Комментарии

Оператор можно использовать `Imports` для определения глобальных пространств имен XML, которые можно использовать с XML-литералами и свойствами осей XML, или как параметры, передаваемые `GetXmlNamespace` оператору. (Сведения об использовании `Imports` инструкции для импорта псевдонима, который можно использовать при использовании имен типов в коде, см. в разделе [оператор Imports (пространство имен .NET и тип)](imports-statement-net-namespace-and-type.md).) Синтаксис объявления пространства имен XML с помощью `Imports` оператора идентичен синтаксису, используемому в XML. Таким образом, можно скопировать объявление пространства имен из XML-файла и использовать его в `Imports` инструкции.

Префиксы пространства имен XML полезны, если требуется многократно создавать XML-элементы из одного и того же пространства имен. Префикс пространства имен XML, объявленный с помощью `Imports` инструкции, является глобальным в том смысле, что он доступен для всего кода в файле. Его можно использовать при создании литералов XML-элементов и при доступе к свойствам осей XML. Дополнительные сведения см. в разделе [литерал XML-элемента](../xml-literals/xml-element-literal.md) и [Свойства оси XML](../xml-axis/index.md).

Если определено глобальное пространство имен XML без префикса пространства имен (например, `Imports <xmlns="http://SomeNameSpace>"` ), это пространство имен считается пространством имен XML по умолчанию. Пространство имен XML по умолчанию используется для любых литералов XML-элементов или свойств оси атрибутов XML, которые явно не задают пространство имен. Пространство имен по умолчанию также используется, если указанное пространство имен представляет собой пустое пространство имен (то есть `xmlns=""` ). Пространство имен XML по умолчанию не применяется к атрибутам XML в XML-литералах или к свойствам оси атрибутов XML, не имеющим пространства имен.

Пространства имен XML, определенные в XML-литерале, которые называются *локальными пространствами имен XML*, имеют приоритет над пространствами имен XML, которые определены `Imports` инструкцией как глобальные. Пространства имен XML, определенные `Imports` инструкцией, имеют приоритет над пространствами имен XML, импортированными для проекта Visual Basic. Если XML-литерал определяет пространство имен XML, это локальное пространство имен не применяется к внедренным выражениям.

Глобальные пространства имен XML следуют тем же правилам области и определения, что и .NET Framework пространства имен. В результате можно включить `Imports` инструкцию для определения глобального пространства имен XML в любом месте, где можно импортировать .NET Framework пространство имен. Сюда входят файлы кода и импортированные пространства имен на уровне проекта. Сведения об импортированных пространствах имен на уровне проекта см. в разделе [Страница "ссылки" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).

Каждый исходный файл может содержать любое количество `Imports` инструкций. Они должны следовать объявлениям параметров, таким как `Option Strict` оператор, и должны предшествовать объявлениям элементов программирования, таким как `Module` операторы или `Class` .

## <a name="example"></a>Пример

В следующем примере выполняется импорт пространства имен XML по умолчанию и пространства имен XML, определенного префиксом `ns` . Затем он создает литералы XML, которые используют оба пространства имен.

[!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]

Этот пример кода отображает следующий текст:

```xml
<ns:outer xmlns="http://DefaultNamespace"
          xmlns:ns="http://NewNamespace">
  <ns:innerElement></ns:innerElement>
  <siblingElement></siblingElement>
  <innerElement />
</ns:outer>
```

## <a name="example"></a>Пример

В следующем примере выполняется импорт префикса пространства имен XML `ns` . Затем он создает XML-литерал, использующий префикс пространства имен, и отображает окончательную форму элемента.

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

Обратите внимание, что компилятор преобразует префикс пространства имен XML из глобального префикса в локальное определение префикса.

## <a name="example"></a>Пример

В следующем примере выполняется импорт префикса пространства имен XML `ns` . Затем префикс пространства имен используется для создания литерала XML и доступа к первому дочернему узлу с полным именем `ns:name`.

[!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]

Этот пример кода отображает следующий текст:

`Patrick Hines`

## <a name="see-also"></a>См. также раздел

- [XML-литерал элемента](../xml-literals/xml-element-literal.md)
- [Свойства оси XML](../xml-axis/index.md)
- [Имена объявленных элементов и атрибутов XML](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [Оператор GetXmlNamespace](../operators/getxmlnamespace-operator.md)
