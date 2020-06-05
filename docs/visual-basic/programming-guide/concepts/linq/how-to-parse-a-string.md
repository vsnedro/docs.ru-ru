---
title: Практическое руководство. Анализ строки
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: 0a9076fc516bb8e6bc74732ca252fabfeda43d53
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398016"
---
# <a name="how-to-parse-a-string-visual-basic"></a>Руководство. анализ строки (Visual Basic)
В этом разделе показано, как создать XML-дерево в C#.  
  
## <a name="example"></a>Пример  
 Можно выполнить синтаксический анализ строки в Visual Basic с помощью `XElement.Parse` метода. Однако более эффективно используются XML-литералы, как показано в следующем коде, поскольку применение XML-литералов не приводит к снижению производительности, в отличие от синтаксического анализа кода XML, полученного из строки.  
  
 Используя литералы XML, можно просто скопировать и вставить XML-код в программу Visual Basic.  
  
> [!NOTE]
> Синтаксический анализ текста или загрузка XML-документа из текстового файла менее эффективны, чем функциональное построение. При инициализации XML-дерева из кода для осуществления функционального построения требуется меньше процессорного времени, чем для синтаксического анализа текста.  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Синтаксический анализ XML (Visual Basic)](parsing-xml.md)
