---
title: <commonBehaviors>
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 55f70157b6759c5e1cb45da20eed928fa1d4a183
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176062"
---
# \<commonBehaviors>

<span data-ttu-id="dade4-101">Раздел `commonBehaviors` может определяться только в файле machine.config.</span><span class="sxs-lookup"><span data-stu-id="dade4-101">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="dade4-102">В нем определяются две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="dade4-102">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="dade4-103">Каждая коллекция определяет элементы поведения, используемые всеми конечными точками и службами WCF на компьютере соответственно.</span><span class="sxs-lookup"><span data-stu-id="dade4-103">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="dade4-104">Поведения, определенные в `endpointBehaviors`, применяются только к клиентам, а поведения, определенные в `serviceBehaviors`, применяются только к службам.</span><span class="sxs-lookup"><span data-stu-id="dade4-104">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="dade4-105">Если поведение определяется как в разделе `commonBehaviors`, так и в разделе `behaviors`, преимущество имеет поведение в разделе `behaviors`.</span><span class="sxs-lookup"><span data-stu-id="dade4-105">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
