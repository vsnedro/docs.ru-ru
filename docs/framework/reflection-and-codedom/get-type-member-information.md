---
title: Практическое руководство. Получение сведений о типах и членах с помощью отражения
description: Узнайте, как использовать пространство имен System.Reflection для получения сведений о типах и членах с помощью отражения.
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: fa7af39c0addb328944a03236c26982301caf722
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865324"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a><span data-ttu-id="01743-103">Практическое руководство. Получение сведений о типах и членах с помощью отражения</span><span class="sxs-lookup"><span data-stu-id="01743-103">How to: Get type and member information by using reflection</span></span>
<span data-ttu-id="01743-104">Пространство имен <xref:System.Reflection> содержит много методов для получения сведений о типах и их членах.</span><span class="sxs-lookup"><span data-stu-id="01743-104">The <xref:System.Reflection> namespace contains many methods for obtaining information about types and their members.</span></span> <span data-ttu-id="01743-105">В этой статье демонстрируется один из этих методов — <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="01743-105">This article demonstrates one of these methods, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="01743-106">Дополнительные сведения см. в разделе [Общие сведения об отражении](reflection.md).</span><span class="sxs-lookup"><span data-stu-id="01743-106">For additional information, see [Reflection overview](reflection.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="01743-107">Пример</span><span class="sxs-lookup"><span data-stu-id="01743-107">Example</span></span>

<span data-ttu-id="01743-108">В следующем примере демонстрируется получение сведений о типах и членах с помощью отражения:</span><span class="sxs-lookup"><span data-stu-id="01743-108">The following example obtains type and member information by using reflection:</span></span>

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a><span data-ttu-id="01743-109">См. также</span><span class="sxs-lookup"><span data-stu-id="01743-109">See also</span></span>

- [<span data-ttu-id="01743-110">Программирование с использованием доменов приложений</span><span class="sxs-lookup"><span data-stu-id="01743-110">Program with application domains</span></span>](../app-domains/application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="01743-111">Отражение</span><span class="sxs-lookup"><span data-stu-id="01743-111">Reflection</span></span>](reflection.md)
- [<span data-ttu-id="01743-112">Использование доменов приложений</span><span class="sxs-lookup"><span data-stu-id="01743-112">Use application domains</span></span>](../app-domains/use.md)
