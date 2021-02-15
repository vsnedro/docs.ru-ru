---
description: Дополнительные сведения см. в статье как загрузить XML из файла, строки или потока (Visual Basic)
title: Практическое руководство. Загрузка XML-кода из файла, строки или потока
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 375190642c93d929abe2ae10bb6ccba927e3bc8a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480067"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Практическое руководство. Загрузка XML-кода из файла, строки или потока (Visual Basic)

Можно создать [XML-литералы](../../../language-reference/xml-literals/index.md) и заполнить их содержимым из внешнего источника, например файла, строки или потока, с помощью нескольких методов. Эти методы показаны в следующих примерах.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a>Загрузка XML из файла

Чтобы заполнить XML-литерал <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> , например объект или, из файла, используйте `Load` метод. Этот метод может принимать в качестве входных данных путь к файлу, поток текста или поток XML.

В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Load%28System.String%29> метода для заполнения <xref:System.Xml.Linq.XDocument> объекта XML из текстового файла.

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a>Загрузка XML из строки

Для заполнения XML-литерала, такого как <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> объект или, из строки можно использовать `Parse` метод.

В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> метода для заполнения <xref:System.Xml.Linq.XDocument> объекта XML из строки.

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a>Загрузка XML из потока

Для заполнения XML-литерала, такого как <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> объект или, из потока можно использовать `Load` метод или <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> .

В следующем примере кода показано использование <xref:System.Xml.Linq.XNode.ReadFrom%2A> метода для заполнения <xref:System.Xml.Linq.XDocument> объекта XML-потоком из XML-потока.

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a>См. также раздел

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [XML-литералы](../../../language-reference/xml-literals/index.md)
- [XML](index.md)
- [Обработка XML в Visual Basic](manipulating-xml.md)
