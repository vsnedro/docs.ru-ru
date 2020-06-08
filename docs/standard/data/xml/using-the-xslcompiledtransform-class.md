---
title: Использование класса XslCompiledTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
ms.openlocfilehash: 8705b4c6324ce20a1f37d3ee864ab494adcdd6a5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281778"
---
# <a name="using-the-xslcompiledtransform-class"></a><span data-ttu-id="d6b68-102">Использование класса XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="d6b68-102">Using the XslCompiledTransform Class</span></span>
<span data-ttu-id="d6b68-103">Класс <xref:System.Xml.Xsl.XslCompiledTransform> является обработчиком XSLT в платформе Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d6b68-103">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the Microsoft .NET Framework XSLT processor.</span></span> <span data-ttu-id="d6b68-104">Этот класс используется для компиляции таблиц стилей и выполнения преобразований XSLT.</span><span class="sxs-lookup"><span data-stu-id="d6b68-104">This class is used to compile style sheets and execute XSLT transformations.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6b68-105">Хотя класс <xref:System.Xml.Xsl.XslCompiledTransform> имеет более высокий общий уровень производительности, чем класс <xref:System.Xml.Xsl.XslTransform>, метод <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> класса <xref:System.Xml.Xsl.XslCompiledTransform> может выполняться медленнее, чем метод <xref:System.Xml.Xsl.XslTransform.Load%2A> класса <xref:System.Xml.Xsl.XslTransform> при первом вызове преобразования.</span><span class="sxs-lookup"><span data-stu-id="d6b68-105">Although the overall performance of the <xref:System.Xml.Xsl.XslCompiledTransform> class is better than the <xref:System.Xml.Xsl.XslTransform> class, the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslCompiledTransform> class might perform more slowly than the <xref:System.Xml.Xsl.XslTransform.Load%2A> method of the <xref:System.Xml.Xsl.XslTransform> class the first time it is called on a transformation.</span></span> <span data-ttu-id="d6b68-106">Причина этого заключается в необходимости компиляции XSLT-файла перед его загрузкой.</span><span class="sxs-lookup"><span data-stu-id="d6b68-106">This is because the XSLT file must be compiled before it is loaded.</span></span> <span data-ttu-id="d6b68-107">Дополнительные сведения см. в следующей записи блога: [XslCompiledTransform выполняется медленнее, чем XslTransform?](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)</span><span class="sxs-lookup"><span data-stu-id="d6b68-107">For more information, see the following blog post: [XslCompiledTransform Slower than XslTransform?](https://docs.microsoft.com/archive/blogs/antosha/xslcompiledtransform-slower-than-xsltransform)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6b68-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d6b68-108">In This Section</span></span>  
 [<span data-ttu-id="d6b68-109">Входные данные для класса XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="d6b68-109">Inputs to the XslCompiledTransform Class</span></span>](inputs-to-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="d6b68-110">Описываются доступные входные параметры XSLT.</span><span class="sxs-lookup"><span data-stu-id="d6b68-110">Describes the available XSLT input options.</span></span>  
  
 [<span data-ttu-id="d6b68-111">Параметры вывода в классе XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="d6b68-111">Output Options on the XslCompiledTransform Class</span></span>](output-options-on-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="d6b68-112">Описываются доступные выходные параметры XSLT.</span><span class="sxs-lookup"><span data-stu-id="d6b68-112">Describes the available XSLT output options.</span></span>  
  
 [<span data-ttu-id="d6b68-113">Разрешение внешних ресурсов в ходе обработки XSLT</span><span class="sxs-lookup"><span data-stu-id="d6b68-113">Resolving External Resources During XSLT Processing</span></span>](resolving-external-resources-during-xslt-processing.md)  
 <span data-ttu-id="d6b68-114">Обсуждается использование класса <xref:System.Xml.XmlResolver> для разрешения внешних ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d6b68-114">Discusses using the <xref:System.Xml.XmlResolver> class to resolve external resources.</span></span>  
  
 [<span data-ttu-id="d6b68-115">Расширение таблиц стилей XSLT</span><span class="sxs-lookup"><span data-stu-id="d6b68-115">Extending XSLT Style Sheets</span></span>](extending-xslt-style-sheets.md)  
 <span data-ttu-id="d6b68-116">Обсуждается поддержка расширений XSLT.</span><span class="sxs-lookup"><span data-stu-id="d6b68-116">Discusses how XSLT extensions are supported.</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="d6b68-117">Устранимые ошибки XSLT</span><span class="sxs-lookup"><span data-stu-id="d6b68-117">Recoverable XSLT Errors</span></span>](recoverable-xslt-errors.md)|<span data-ttu-id="d6b68-118">Содержит список поведений по выбору, допустимых в соответствии с рекомендациями консорциума W3C по XSLT 1.0, и описывает, каким образом эти поведения обрабатываются классом <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="d6b68-118">Lists discretionary behaviors allowed by the World Wide Web Consortium (W3C) XSLT 1.0 recommendation and describes how these behaviors are handled by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>|  
|[<span data-ttu-id="d6b68-119">Практическое руководство. Преобразование фрагмента узла</span><span class="sxs-lookup"><span data-stu-id="d6b68-119">How to: Transform a Node Fragment</span></span>](how-to-transform-a-node-fragment.md)|<span data-ttu-id="d6b68-120">Описывает процесс преобразования фрагмента узла.</span><span class="sxs-lookup"><span data-stu-id="d6b68-120">Describes how to transform a node fragment.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="d6b68-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d6b68-121">Related Sections</span></span>  
 [<span data-ttu-id="d6b68-122">Миграция с класса XslTransform</span><span class="sxs-lookup"><span data-stu-id="d6b68-122">Migrating From the XslTransform Class</span></span>](migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="d6b68-123">Обсуждается перенос кода из класса <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="d6b68-123">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b68-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d6b68-124">See also</span></span>

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
