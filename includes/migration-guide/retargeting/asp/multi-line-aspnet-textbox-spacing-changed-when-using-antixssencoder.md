---
ms.openlocfilehash: 150b98255b3075a8fe8cad60ce234206b788a5f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617270"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a><span data-ttu-id="ad6c3-101">Изменены интервалы многострочного текстового поля ASP.NET при использовании AntiXSSEncoder</span><span class="sxs-lookup"><span data-stu-id="ad6c3-101">Multi-line ASP.Net TextBox spacing changed when using AntiXSSEncoder</span></span>

#### <a name="details"></a><span data-ttu-id="ad6c3-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ad6c3-102">Details</span></span>

<span data-ttu-id="ad6c3-103">В .NET Framework 4.0 между строками многострочного текстового поля при обратной передаче вставлялись дополнительные строки, если использовался <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="ad6c3-103">In .NET Framework 4.0, extra lines were inserted between lines of a multi-line text box on postback, if using the <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>.</span></span> <span data-ttu-id="ad6c3-104">В .NET Framework 4.5 эти дополнительные разрывы строк отсутствуют только в том случае, если веб-приложение предназначено для .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="ad6c3-104">In .NET Framework 4.5, those extra line breaks are not included, but only if the web app is targeting .NET Framework 4.5</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ad6c3-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="ad6c3-105">Suggestion</span></span>

<span data-ttu-id="ad6c3-106">Имейте в виду, что в веб-приложениях 4.0, перенаправленных на .NET Framework 4.5, многострочные текстовые поля могут быть усовершенствованы, чтобы больше не вставлять дополнительные разрывы строк.</span><span class="sxs-lookup"><span data-stu-id="ad6c3-106">Be aware that 4.0 web apps retargeted to .NET Framework 4.5 may have multi-line text boxes improved to no longer insert extra line breaks.</span></span> <span data-ttu-id="ad6c3-107">Если это нежелательно, для приложения, выполняющегося в .NET Framework 4.5, можно сохранить старое поведение путем изменения версии платформы на .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="ad6c3-107">If this is not desirable, the app  can have the old behavior when running on .NET Framework 4.5 by targeting the .NET Framework 4.0.</span></span>

| <span data-ttu-id="ad6c3-108">name</span><span class="sxs-lookup"><span data-stu-id="ad6c3-108">Name</span></span>    | <span data-ttu-id="ad6c3-109">Значение</span><span class="sxs-lookup"><span data-stu-id="ad6c3-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ad6c3-110">Область</span><span class="sxs-lookup"><span data-stu-id="ad6c3-110">Scope</span></span>   | <span data-ttu-id="ad6c3-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="ad6c3-111">Minor</span></span>       |
| <span data-ttu-id="ad6c3-112">Version</span><span class="sxs-lookup"><span data-stu-id="ad6c3-112">Version</span></span> | <span data-ttu-id="ad6c3-113">4.5</span><span class="sxs-lookup"><span data-stu-id="ad6c3-113">4.5</span></span>         |
| <span data-ttu-id="ad6c3-114">Type</span><span class="sxs-lookup"><span data-stu-id="ad6c3-114">Type</span></span>    | <span data-ttu-id="ad6c3-115">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="ad6c3-115">Retargeting</span></span> |
