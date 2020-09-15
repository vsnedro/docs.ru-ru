---
ms.openlocfilehash: c967a5b09b5e9ffeee7bff046f0c96469bc7fb02
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615658"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="e24c6-101">ClickOnce поддерживает SHA-256 в приложениях, предназначенных для версии 4.0</span><span class="sxs-lookup"><span data-stu-id="e24c6-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

#### <a name="details"></a><span data-ttu-id="e24c6-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="e24c6-102">Details</span></span>

<span data-ttu-id="e24c6-103">Раньше приложению ClickOnce с сертификатом, подписанным с SHA-256, требовалась платформа .NET Framework 4.5 или более поздней версии, даже если приложение предназначено для версии 4.0.</span><span class="sxs-lookup"><span data-stu-id="e24c6-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="e24c6-104">Теперь приложения ClickOnce, предназначенные для .NET Framework 4.0, можно запускать на .NET Framework 4.0, даже если они подписаны с помощью алгоритма SHA-256.</span><span class="sxs-lookup"><span data-stu-id="e24c6-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e24c6-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="e24c6-105">Suggestion</span></span>

<span data-ttu-id="e24c6-106">Это изменение удаляет зависимость и позволяет использовать сертификаты SHA-256 для подписи приложений ClickOnce на платформе .NET Framework 4 и более ранних версий.</span><span class="sxs-lookup"><span data-stu-id="e24c6-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>

| <span data-ttu-id="e24c6-107">name</span><span class="sxs-lookup"><span data-stu-id="e24c6-107">Name</span></span>    | <span data-ttu-id="e24c6-108">Значение</span><span class="sxs-lookup"><span data-stu-id="e24c6-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e24c6-109">Область</span><span class="sxs-lookup"><span data-stu-id="e24c6-109">Scope</span></span>   | <span data-ttu-id="e24c6-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="e24c6-110">Minor</span></span>       |
| <span data-ttu-id="e24c6-111">Version</span><span class="sxs-lookup"><span data-stu-id="e24c6-111">Version</span></span> | <span data-ttu-id="e24c6-112">4.6</span><span class="sxs-lookup"><span data-stu-id="e24c6-112">4.6</span></span>         |
| <span data-ttu-id="e24c6-113">Type</span><span class="sxs-lookup"><span data-stu-id="e24c6-113">Type</span></span>    | <span data-ttu-id="e24c6-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="e24c6-114">Retargeting</span></span> |
