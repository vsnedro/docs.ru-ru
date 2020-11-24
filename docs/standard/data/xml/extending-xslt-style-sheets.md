---
title: Расширение таблиц стилей XSLT
ms.date: 03/30/2017
ms.assetid: df4ba2bf-a99e-4d22-bbf3-04fc67669dbc
ms.openlocfilehash: e598cb497ba1d415a3ccb53f1583352eba4ccdbb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831238"
---
# <a name="extending-xslt-style-sheets"></a><span data-ttu-id="0da9c-102">Расширение таблиц стилей XSLT</span><span class="sxs-lookup"><span data-stu-id="0da9c-102">Extending XSLT Style Sheets</span></span>
<span data-ttu-id="0da9c-103">В этом разделе описаны различные методы расширения функциональных возможностей XSLT.</span><span class="sxs-lookup"><span data-stu-id="0da9c-103">This section describes the different methods of extending the XSLT functionality.</span></span> <span data-ttu-id="0da9c-104">С помощью класса <xref:System.Xml.Xsl.XsltArgumentList> можно добавлять объекты расширения или параметры.</span><span class="sxs-lookup"><span data-stu-id="0da9c-104">You can add extension objects or parameters using the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span> <span data-ttu-id="0da9c-105">Затем объекты расширения или параметры можно вызывать из таблицы стилей.</span><span class="sxs-lookup"><span data-stu-id="0da9c-105">The extension objects or parameters can then be called from the style sheet.</span></span> <span data-ttu-id="0da9c-106">Кроме того, можно внедрять в таблицу стилей блоки скрипта с помощью элемента `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="0da9c-106">In addition, you can also embed script blocks into the style sheet by using the `msxsl:script` element.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0da9c-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="0da9c-107">In This Section</span></span>  
 [<span data-ttu-id="0da9c-108">Объекты расширения XSLT</span><span class="sxs-lookup"><span data-stu-id="0da9c-108">XSLT Extension Objects</span></span>](xslt-extension-objects.md)  
 <span data-ttu-id="0da9c-109">Обсуждается использование класса <xref:System.Xml.Xsl.XsltArgumentList> для обработки объектов расширения XSLT.</span><span class="sxs-lookup"><span data-stu-id="0da9c-109">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT extension objects.</span></span>  
  
 [<span data-ttu-id="0da9c-110">Параметры XSLT</span><span class="sxs-lookup"><span data-stu-id="0da9c-110">XSLT Parameters</span></span>](xslt-parameters.md)  
 <span data-ttu-id="0da9c-111">Обсуждается использование класса <xref:System.Xml.Xsl.XsltArgumentList> для обработки параметров XSLT.</span><span class="sxs-lookup"><span data-stu-id="0da9c-111">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT parameters.</span></span>  
  
 [<span data-ttu-id="0da9c-112">Блоки скриптов с использованием msxsl:script</span><span class="sxs-lookup"><span data-stu-id="0da9c-112">Script Blocks Using msxsl:script</span></span>](script-blocks-using-msxsl-script.md)  
 <span data-ttu-id="0da9c-113">Обсуждается использование элемента `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="0da9c-113">Discusses using the `msxsl:script` element.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0da9c-114">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0da9c-114">Related Sections</span></span>  
 [<span data-ttu-id="0da9c-115">Преобразования XSLT</span><span class="sxs-lookup"><span data-stu-id="0da9c-115">XSLT Transformations</span></span>](xslt-transformations.md)
