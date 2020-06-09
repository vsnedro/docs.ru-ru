---
title: Поиск утверждений в наборах утверждений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], finding in a claimset
- claims [WCF]
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
ms.openlocfilehash: 1954da20d382630f965582fcc01bbaf72665720a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595457"
---
# <a name="finding-claims-in-a-claimset"></a><span data-ttu-id="92ba5-102">Поиск утверждений в наборах утверждений</span><span class="sxs-lookup"><span data-stu-id="92ba5-102">Finding Claims in a ClaimSet</span></span>
<span data-ttu-id="92ba5-103">При использовании авторизации на основе утверждений часто выполняется проверка содержимого <xref:System.IdentityModel.Claims.ClaimSet> для определенных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="92ba5-103">Examining the content of a <xref:System.IdentityModel.Claims.ClaimSet> for particular types of claims is a common task when using claim-based authorization.</span></span> <span data-ttu-id="92ba5-104">Чтобы проверить <xref:System.IdentityModel.Claims.ClaimSet> на наличие определенных утверждений, используйте метод <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A>.</span><span class="sxs-lookup"><span data-stu-id="92ba5-104">To examine a <xref:System.IdentityModel.Claims.ClaimSet> for the presence of particular claims, use the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> method.</span></span> <span data-ttu-id="92ba5-105">Этот метод обеспечивает более высокую производительность по сравнению с выполнением итерации непосредственно с <xref:System.IdentityModel.Claims.ClaimSet>.</span><span class="sxs-lookup"><span data-stu-id="92ba5-105">This method provides better performance than iterating directly over the <xref:System.IdentityModel.Claims.ClaimSet>.</span></span> <span data-ttu-id="92ba5-106">Использование этого метода показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="92ba5-106">The following example demonstrates this usage.</span></span> <span data-ttu-id="92ba5-107">Обратите внимание, что параметры `claimType` и `claimRight` могут иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="92ba5-107">Note that the `claimType` and `claimRight` parameters can be `null`.</span></span> <span data-ttu-id="92ba5-108">В этом случае параметры будут соответствовать всем типам и правам утверждения.</span><span class="sxs-lookup"><span data-stu-id="92ba5-108">In that case, the parameters will match all claim types and claim rights.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92ba5-109">Пример</span><span class="sxs-lookup"><span data-stu-id="92ba5-109">Example</span></span>  
 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="92ba5-110">См. также</span><span class="sxs-lookup"><span data-stu-id="92ba5-110">See also</span></span>

- [<span data-ttu-id="92ba5-111">Управление утверждениями и авторизацией с помощью модели удостоверения</span><span class="sxs-lookup"><span data-stu-id="92ba5-111">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)
