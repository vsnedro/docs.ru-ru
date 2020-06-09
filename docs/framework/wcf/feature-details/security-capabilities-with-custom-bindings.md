---
title: Возможности безопасности при использовании пользовательских привязок
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 48d17543f2b133c74bcfa82cfe1a2a0de28b1d01
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595197"
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="452b2-102">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="452b2-102">Security Capabilities with Custom Bindings</span></span>
<span data-ttu-id="452b2-103">Основные задачи обеспечения безопасности можно выполнить, используя одну из предоставляемых системой привязок.</span><span class="sxs-lookup"><span data-stu-id="452b2-103">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="452b2-104">Однако при необходимости в дополнительных элементах управления можно создать пользовательскую привязку с помощью элемента <xref:System.ServiceModel.Channels.SecurityBindingElement>, следуя объяснениям в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="452b2-104">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> <span data-ttu-id="452b2-105">Дополнительные сведения о пользовательских привязках см. в разделе [пользовательские привязки](../extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="452b2-105">For more information about custom bindings, see [Custom Bindings](../extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="452b2-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="452b2-106">In This Section</span></span>  
 [<span data-ttu-id="452b2-107">Режимы проверки подлинности SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="452b2-107">SecurityBindingElement Authentication Modes</span></span>](securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="452b2-108">Содержит описание режимов проверки подлинности, которые возможны для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="452b2-108">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="452b2-109">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="452b2-109">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="452b2-110">Содержит описание основных шагов, которые необходимо предпринять для создания пользовательской привязки к элементу безопасности.</span><span class="sxs-lookup"><span data-stu-id="452b2-110">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="452b2-111">Практическое руководство. Создание SecurityBindingElement для заданного режима проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="452b2-111">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="452b2-112">Описывается, как создать элемент безопасности для заданного режима проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="452b2-112">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="452b2-113">Практическое руководство. Порядок отключения безопасных сеансов в WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="452b2-113">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="452b2-114">Описывается, как отключить безопасные сеансы при создании службы федерации.</span><span class="sxs-lookup"><span data-stu-id="452b2-114">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="452b2-115">Практическое руководство. Включение обнаружения повтора сообщений</span><span class="sxs-lookup"><span data-stu-id="452b2-115">How to: Enable Message Replay Detection</span></span>](how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="452b2-116">Описывается, как определить, когда будет осуществлена атака воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="452b2-116">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="452b2-117">Практическое руководство. Создание подтверждающих учетных данных</span><span class="sxs-lookup"><span data-stu-id="452b2-117">How to: Create a Supporting Credential</span></span>](how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="452b2-118">Описывается, как предоставить службе подтверждающие учетные данные при необходимости.</span><span class="sxs-lookup"><span data-stu-id="452b2-118">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="452b2-119">Практическое руководство. Настройка подтверждения сигнатуры</span><span class="sxs-lookup"><span data-stu-id="452b2-119">How to: Set Up a Signature Confirmation</span></span>](how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="452b2-120">Содержит описание шагов, которые необходимо предпринять для подтверждения подписей при использовании цифровых подписей сообщений.</span><span class="sxs-lookup"><span data-stu-id="452b2-120">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="452b2-121">Практическое руководство. Установка максимальной разницы в показаниях часов</span><span class="sxs-lookup"><span data-stu-id="452b2-121">How to: Set a Max Clock Skew</span></span>](how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="452b2-122">Описывается, как настроить максимально допустимую разницу во времени между службой и клиентом.</span><span class="sxs-lookup"><span data-stu-id="452b2-122">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="452b2-123">Практическое руководство. Выключение шифрования цифровых сигнатур</span><span class="sxs-lookup"><span data-stu-id="452b2-123">How to: Disable Encryption of Digital Signatures</span></span>](how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="452b2-124">Описывается, как отключение шифрования цифровых подписей может увеличить производительность.</span><span class="sxs-lookup"><span data-stu-id="452b2-124">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="452b2-125">Справочник</span><span class="sxs-lookup"><span data-stu-id="452b2-125">Reference</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="452b2-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="452b2-126">Related Sections</span></span>  
 [<span data-ttu-id="452b2-127">Основные сведения об уровне защиты</span><span class="sxs-lookup"><span data-stu-id="452b2-127">Understanding Protection Level</span></span>](../understanding-protection-level.md)  
  
 [<span data-ttu-id="452b2-128">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="452b2-128">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="452b2-129">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="452b2-129">See also</span></span>

- [<span data-ttu-id="452b2-130">Привязки и безопасность</span><span class="sxs-lookup"><span data-stu-id="452b2-130">Bindings and Security</span></span>](bindings-and-security.md)
- [<span data-ttu-id="452b2-131">Обзор безопасности</span><span class="sxs-lookup"><span data-stu-id="452b2-131">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="452b2-132">Привязки, предоставляемые системой</span><span class="sxs-lookup"><span data-stu-id="452b2-132">System-Provided Bindings</span></span>](../system-provided-bindings.md)
