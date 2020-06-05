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
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="1800a-102">Руководство. анализ строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1800a-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="1800a-103">В этом разделе показано, как создать XML-дерево в C#.</span><span class="sxs-lookup"><span data-stu-id="1800a-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1800a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="1800a-104">Example</span></span>  
 <span data-ttu-id="1800a-105">Можно выполнить синтаксический анализ строки в Visual Basic с помощью `XElement.Parse` метода.</span><span class="sxs-lookup"><span data-stu-id="1800a-105">You can parse a string in Visual Basic by using the `XElement.Parse` method.</span></span> <span data-ttu-id="1800a-106">Однако более эффективно используются XML-литералы, как показано в следующем коде, поскольку применение XML-литералов не приводит к снижению производительности, в отличие от синтаксического анализа кода XML, полученного из строки.</span><span class="sxs-lookup"><span data-stu-id="1800a-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="1800a-107">Используя литералы XML, можно просто скопировать и вставить XML-код в программу Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1800a-107">By using XML literals, you can just copy and paste your XML into your Visual Basic program.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1800a-108">Синтаксический анализ текста или загрузка XML-документа из текстового файла менее эффективны, чем функциональное построение.</span><span class="sxs-lookup"><span data-stu-id="1800a-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="1800a-109">При инициализации XML-дерева из кода для осуществления функционального построения требуется меньше процессорного времени, чем для синтаксического анализа текста.</span><span class="sxs-lookup"><span data-stu-id="1800a-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1800a-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1800a-110">See also</span></span>

- [<span data-ttu-id="1800a-111">Синтаксический анализ XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1800a-111">Parsing XML (Visual Basic)</span></span>](parsing-xml.md)
