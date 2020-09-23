---
title: VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
ms.openlocfilehash: 7193d1f635ff877ab5d07f03584f19f5ce18138a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059372"
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a><span data-ttu-id="d39c1-102">VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе</span><span class="sxs-lookup"><span data-stu-id="d39c1-102">VbStrConv.Wide and VbStrConv.Narrow cannot be combined</span></span>

<span data-ttu-id="d39c1-103">Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `Wide` перечисления `Narrow`.</span><span class="sxs-lookup"><span data-stu-id="d39c1-103">Your application is trying to combine the `VbStrConv` enumeration members `Wide` and `Narrow`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d39c1-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d39c1-104">To correct this error</span></span>  
  
1. <span data-ttu-id="d39c1-105">Удалите `VbStrConv.Wide` или `VbStrConv.Narrow`.</span><span class="sxs-lookup"><span data-stu-id="d39c1-105">Remove either `VbStrConv.Wide` or `VbStrConv.Narrow`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d39c1-106">См. также</span><span class="sxs-lookup"><span data-stu-id="d39c1-106">See also</span></span>

- <xref:System.Globalization>

- [<span data-ttu-id="d39c1-107">Разработка глобализованных и локализованных приложений</span><span class="sxs-lookup"><span data-stu-id="d39c1-107">Develop globalized and localized apps</span></span>](/visualstudio/ide/globalizing-and-localizing-applications)
