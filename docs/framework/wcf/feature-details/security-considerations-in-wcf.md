---
title: Вопросы безопасности в WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: ed0f018e0151e68afeb9a4747bf8a260faa184b1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601040"
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="e2a3a-102">Вопросы безопасности в WCF</span><span class="sxs-lookup"><span data-stu-id="e2a3a-102">Security Considerations in WCF</span></span>
<span data-ttu-id="e2a3a-103">В подразделах этого раздела перечислены различные элементы, связанные с безопасностью, которые следует учитывать при проектировании приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e2a3a-103">The topics in this section list various security-related items to consider when designing a Windows Communication Foundation (WCF) application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e2a3a-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e2a3a-104">In This Section</span></span>  
 [<span data-ttu-id="e2a3a-105">Раскрытие информации</span><span class="sxs-lookup"><span data-stu-id="e2a3a-105">Information Disclosure</span></span>](information-disclosure.md)  
 <span data-ttu-id="e2a3a-106">Описание различных способов раскрытия информации и атак, а также способов их предотвращения.</span><span class="sxs-lookup"><span data-stu-id="e2a3a-106">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="e2a3a-107">Повышение привилегий</span><span class="sxs-lookup"><span data-stu-id="e2a3a-107">Elevation of Privilege</span></span>](elevation-of-privilege.md)  
 <span data-ttu-id="e2a3a-108">Описание последствий предоставления злоумышленнику более широких прав по сравнению с правами, предоставленными ему изначально, и способов решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="e2a3a-108">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="e2a3a-109">Отказ в обслуживании</span><span class="sxs-lookup"><span data-stu-id="e2a3a-109">Denial of Service</span></span>](denial-of-service.md)  
 <span data-ttu-id="e2a3a-110">Описание ситуаций, когда система не может обрабатывать сообщения должным образом, и способов решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="e2a3a-110">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="e2a3a-111">незаконное изменение;</span><span class="sxs-lookup"><span data-stu-id="e2a3a-111">Tampering</span></span>](tampering.md)  
 <span data-ttu-id="e2a3a-112">Описание изменения сообщений или доставки сообщений, а также способов решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="e2a3a-112">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="e2a3a-113">Атаки с повторением</span><span class="sxs-lookup"><span data-stu-id="e2a3a-113">Replay Attacks</span></span>](replay-attacks.md)  
 <span data-ttu-id="e2a3a-114">Описание последствий копирования злоумышленником потока сообщений между двумя сторонами и воспроизведения этого потока для одной или нескольких сторон, а также способов решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="e2a3a-114">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="e2a3a-115">Соображения о защите безопасных сеансов</span><span class="sxs-lookup"><span data-stu-id="e2a3a-115">Security Considerations for Secure Sessions</span></span>](security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="e2a3a-116">Описание следующих элементов, влияющих на безопасность при реализации безопасных сеансов.</span><span class="sxs-lookup"><span data-stu-id="e2a3a-116">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="e2a3a-117">Неподдерживаемые сценарии</span><span class="sxs-lookup"><span data-stu-id="e2a3a-117">Unsupported Scenarios</span></span>](unsupported-scenarios.md)  
 <span data-ttu-id="e2a3a-118">Перечисление различных сценариев, которые не поддерживают определенный аспект безопасности, и которых следует избегать или учитывать.</span><span class="sxs-lookup"><span data-stu-id="e2a3a-118">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e2a3a-119">Справочник</span><span class="sxs-lookup"><span data-stu-id="e2a3a-119">Reference</span></span>  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="e2a3a-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e2a3a-120">Related Sections</span></span>  
 [<span data-ttu-id="e2a3a-121">Руководство и рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="e2a3a-121">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="e2a3a-122">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="e2a3a-122">See also</span></span>

- [<span data-ttu-id="e2a3a-123">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e2a3a-123">Security</span></span>](security.md)
