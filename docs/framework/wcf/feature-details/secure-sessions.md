---
title: Безопасные сеансы
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: cb02adc7514e27175088e7664b12e45bc8ca5cd9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590089"
---
# <a name="secure-sessions"></a><span data-ttu-id="caeca-102">Безопасные сеансы</span><span class="sxs-lookup"><span data-stu-id="caeca-102">Secure Sessions</span></span>
<span data-ttu-id="caeca-103">Компонент Windows Communication Foundation (WCF) — это надежные сеансы, которые гарантируют получение сообщений в том порядке, в котором они были отправлены.</span><span class="sxs-lookup"><span data-stu-id="caeca-103">A feature of Windows Communication Foundation (WCF) is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="caeca-104">В этом разделе рассматриваются проблемы безопасности, которые необходимо учитывать при создании надежного сеанса.</span><span class="sxs-lookup"><span data-stu-id="caeca-104">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="caeca-105">Дополнительные сведения о надежных сеансах см. [в разделе Использование сеансов](../using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="caeca-105">For more information about reliable sessions, see [Using Sessions](../using-sessions.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="caeca-106">Если в ОС Windows XP требуется олицетворение, следует использовать безопасный сеанс без маркера контекста безопасности с отслеживанием состояния (SCT).</span><span class="sxs-lookup"><span data-stu-id="caeca-106">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="caeca-107">При использовании маркеров SCT с отслеживанием состояния вместе с олицетворением возникает исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="caeca-107">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="caeca-108">Дополнительные сведения см. в разделе [неподдерживаемые сценарии](unsupported-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="caeca-108">For more information, see [Unsupported Scenarios](unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="caeca-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="caeca-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="caeca-110">Безопасные диалоги и безопасные сеансы</span><span class="sxs-lookup"><span data-stu-id="caeca-110">Secure Conversations and Secure Sessions</span></span>](secure-conversations-and-secure-sessions.md)|<span data-ttu-id="caeca-111">Безопасные диалоги и безопасные сеансы - это синонимы.</span><span class="sxs-lookup"><span data-stu-id="caeca-111">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="caeca-112">В этом разделе рассматривается, как работает безопасный диалог, а также когда и почему следует использовать шаблон.</span><span class="sxs-lookup"><span data-stu-id="caeca-112">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="caeca-113">Практическое руководство. Создание сеанса безопасности</span><span class="sxs-lookup"><span data-stu-id="caeca-113">How to: Create a Secure Session</span></span>](how-to-create-a-secure-session.md)|<span data-ttu-id="caeca-114">Пошаговое руководство по основным этапам создания безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="caeca-114">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="caeca-115">Практическое руководство. Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса</span><span class="sxs-lookup"><span data-stu-id="caeca-115">How to: Create a Security Context Token for a Secure Session</span></span>](how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="caeca-116">Пошаговое руководство по созданию веб-фермы, которая будет поддерживать состояние и сеансы с клиентами.</span><span class="sxs-lookup"><span data-stu-id="caeca-116">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="caeca-117">Соображения о защите безопасных сеансов</span><span class="sxs-lookup"><span data-stu-id="caeca-117">Security Considerations for Secure Sessions</span></span>](security-considerations-for-secure-sessions.md)|<span data-ttu-id="caeca-118">Описание некоторых особенностей безопасных сеансов.</span><span class="sxs-lookup"><span data-stu-id="caeca-118">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="caeca-119">Справочник</span><span class="sxs-lookup"><span data-stu-id="caeca-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="caeca-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="caeca-120">Related Sections</span></span>  
 [<span data-ttu-id="caeca-121">Сеансы, экземпляры и параллелизм</span><span class="sxs-lookup"><span data-stu-id="caeca-121">Sessions, Instancing, and Concurrency</span></span>](sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="caeca-122">Проектирование и реализация служб</span><span class="sxs-lookup"><span data-stu-id="caeca-122">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="caeca-123">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="caeca-123">See also</span></span>

- [<span data-ttu-id="caeca-124">Практическое руководство. Включение обнаружения повтора сообщений</span><span class="sxs-lookup"><span data-stu-id="caeca-124">How to: Enable Message Replay Detection</span></span>](how-to-enable-message-replay-detection.md)
- [<span data-ttu-id="caeca-125">Атаки с повторением</span><span class="sxs-lookup"><span data-stu-id="caeca-125">Replay Attacks</span></span>](replay-attacks.md)
- [<span data-ttu-id="caeca-126">Практическое руководство. Создание службы, для которой требуются сеансы</span><span class="sxs-lookup"><span data-stu-id="caeca-126">How to: Create a Service That Requires Sessions</span></span>](how-to-create-a-service-that-requires-sessions.md)
