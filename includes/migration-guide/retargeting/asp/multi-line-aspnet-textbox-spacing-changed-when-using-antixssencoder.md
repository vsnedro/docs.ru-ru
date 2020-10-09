---
ms.openlocfilehash: 53860bb867522503c5cb9bd35e25fadd00a116a2
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609169"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a><span data-ttu-id="1c2b2-101">Изменены интервалы многострочного текстового поля ASP.NET при использовании AntiXSSEncoder</span><span class="sxs-lookup"><span data-stu-id="1c2b2-101">Multi-line ASP.NET TextBox spacing changed when using AntiXSSEncoder</span></span>

#### <a name="details"></a><span data-ttu-id="1c2b2-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="1c2b2-102">Details</span></span>

<span data-ttu-id="1c2b2-103">В .NET Framework 4.0 между строками многострочного текстового поля при обратной передаче вставлялись дополнительные строки, если использовался <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="1c2b2-103">In .NET Framework 4.0, extra lines were inserted between lines of a multi-line text box on postback, if using the <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>.</span></span> <span data-ttu-id="1c2b2-104">В .NET Framework 4.5 эти дополнительные разрывы строк отсутствуют только в том случае, если веб-приложение предназначено для .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="1c2b2-104">In .NET Framework 4.5, those extra line breaks are not included, but only if the web app is targeting .NET Framework 4.5</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1c2b2-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="1c2b2-105">Suggestion</span></span>

<span data-ttu-id="1c2b2-106">Имейте в виду, что в веб-приложениях 4.0, перенаправленных на .NET Framework 4.5, многострочные текстовые поля могут быть усовершенствованы, чтобы больше не вставлять дополнительные разрывы строк.</span><span class="sxs-lookup"><span data-stu-id="1c2b2-106">Be aware that 4.0 web apps retargeted to .NET Framework 4.5 may have multi-line text boxes improved to no longer insert extra line breaks.</span></span> <span data-ttu-id="1c2b2-107">Если это нежелательно, для приложения, выполняющегося в .NET Framework 4.5, можно сохранить старое поведение путем изменения версии платформы на .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="1c2b2-107">If this is not desirable, the app  can have the old behavior when running on .NET Framework 4.5 by targeting the .NET Framework 4.0.</span></span>

| <span data-ttu-id="1c2b2-108">name</span><span class="sxs-lookup"><span data-stu-id="1c2b2-108">Name</span></span>    | <span data-ttu-id="1c2b2-109">Значение</span><span class="sxs-lookup"><span data-stu-id="1c2b2-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1c2b2-110">Область</span><span class="sxs-lookup"><span data-stu-id="1c2b2-110">Scope</span></span>   | <span data-ttu-id="1c2b2-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="1c2b2-111">Minor</span></span>       |
| <span data-ttu-id="1c2b2-112">Version</span><span class="sxs-lookup"><span data-stu-id="1c2b2-112">Version</span></span> | <span data-ttu-id="1c2b2-113">4.5</span><span class="sxs-lookup"><span data-stu-id="1c2b2-113">4.5</span></span>         |
| <span data-ttu-id="1c2b2-114">Type</span><span class="sxs-lookup"><span data-stu-id="1c2b2-114">Type</span></span>    | <span data-ttu-id="1c2b2-115">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="1c2b2-115">Retargeting</span></span> |
