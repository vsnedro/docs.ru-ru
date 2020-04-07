---
title: Аутентификация и авторизация в облачных приложениях
description: Архитектура облачных приложений Native .NET для Azure (ru) Аутентификация и авторизация в облачных местных приложениях
ms.date: 03/02/2020
ms.openlocfilehash: 6261a0a72405bc1c984a04a7851aea4dd6664ddf
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805544"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a><span data-ttu-id="67408-103">Проверка подлинности и авторизация в приложениях, ориентированных на облако</span><span class="sxs-lookup"><span data-stu-id="67408-103">Authentication and authorization in cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="67408-104">*Аутентификация* — это процесс определения личности директора службы безопасности.</span><span class="sxs-lookup"><span data-stu-id="67408-104">*Authentication* is the process of determining the identity of a security principal.</span></span> <span data-ttu-id="67408-105">*Авторизация* — это акт предоставления проверенного основного разрешения на выполнение действия или доступ к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="67408-105">*Authorization* is the act of granting an authenticated principal permission to perform an action or access a resource.</span></span> <span data-ttu-id="67408-106">Иногда аутентификация `AuthN` сокращается до `AuthZ`и авторизация сокращается до .</span><span class="sxs-lookup"><span data-stu-id="67408-106">Sometimes authentication is shortened to `AuthN` and authorization is shortened to `AuthZ`.</span></span> <span data-ttu-id="67408-107">Облачные приложения должны полагаться на открытые протоколы на основе HTTP для проверки подлинности принципов безопасности, так как клиенты и приложения могут работать в любой точке мира на любой платформе или устройстве.</span><span class="sxs-lookup"><span data-stu-id="67408-107">Cloud-native applications need to rely on open HTTP-based protocols to authenticate security principals since both clients and applications could be running anywhere in the world on any platform or device.</span></span> <span data-ttu-id="67408-108">Единственным общим фактором является HTTP.</span><span class="sxs-lookup"><span data-stu-id="67408-108">The only common factor is HTTP.</span></span>

<span data-ttu-id="67408-109">Многие организации по-прежнему полагаются на локальные службы аутентификации, такие как Active Directory Federation Services (ADFS).</span><span class="sxs-lookup"><span data-stu-id="67408-109">Many organizations still rely on local authentication services like Active Directory Federation Services (ADFS).</span></span> <span data-ttu-id="67408-110">Хотя этот подход традиционно хорошо служил организациям в удовлетворении потребностей в аутентификации помещений, облачные приложения получают пользу от систем, разработанных специально для облака.</span><span class="sxs-lookup"><span data-stu-id="67408-110">While this approach has traditionally served organizations well for on premises authentication needs, cloud-native applications benefit from systems designed specifically for the cloud.</span></span> <span data-ttu-id="67408-111">В недавнем консультативном заключении Национального центра кибербезопасности Соединенного Королевства (NCSC) за 2019 год говорится, что «организации, использующие Azure AD в качестве основного источника аутентификации, фактически снизят риск по сравнению с ADFS».</span><span class="sxs-lookup"><span data-stu-id="67408-111">A recent 2019 United Kingdom National Cyber Security Centre (NCSC) advisory states that "organizations using Azure AD as their primary authentication source will actually lower their risk compared to ADFS."</span></span> <span data-ttu-id="67408-112">Некоторые причины, изложенные в [этом анализе,](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) включают:</span><span class="sxs-lookup"><span data-stu-id="67408-112">Some reasons outlined in [this analysis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) include:</span></span>

- <span data-ttu-id="67408-113">Доступ к полному набору технологий защиты учетных данных Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="67408-113">Access to full set of Microsoft credential protection technologies.</span></span>
- <span data-ttu-id="67408-114">Большинство организаций уже в некоторой степени полагаются на Azure AD.</span><span class="sxs-lookup"><span data-stu-id="67408-114">Most organizations are already relying on Azure AD to some extent.</span></span>
- <span data-ttu-id="67408-115">Двойное хэширование хэшов NTLM гарантирует, что компромисс не позволит учетным данным, работающим в локальном Active Directory.</span><span class="sxs-lookup"><span data-stu-id="67408-115">Double hashing of NTLM hashes ensures compromise won't allow credentials that work in local Active Directory.</span></span>

## <a name="references"></a><span data-ttu-id="67408-116">Ссылки</span><span class="sxs-lookup"><span data-stu-id="67408-116">References</span></span>

- [<span data-ttu-id="67408-117">Основные сведения об аутентификации</span><span class="sxs-lookup"><span data-stu-id="67408-117">Authentication basics</span></span>](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [<span data-ttu-id="67408-118">Токены доступа и претензии</span><span class="sxs-lookup"><span data-stu-id="67408-118">Access tokens and claims</span></span>](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [<span data-ttu-id="67408-119">Это может быть время, чтобы канаву вашего на помещение аутентификации услуг</span><span class="sxs-lookup"><span data-stu-id="67408-119">It may be time to ditch your on premises authentication services</span></span>](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
><span data-ttu-id="67408-120">[Назад](identity.md)
>[Вперед](azure-active-directory.md)</span><span class="sxs-lookup"><span data-stu-id="67408-120">[Previous](identity.md)
[Next](azure-active-directory.md)</span></span>
