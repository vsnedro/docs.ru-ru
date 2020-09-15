---
ms.openlocfilehash: cef8096c971da8ae245ff974697022f350cb9195
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616073"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="7dd2b-101">VB.NET больше не поддерживает частичные квалификации пространства имен для API-интерфейсов System.Windows</span><span class="sxs-lookup"><span data-stu-id="7dd2b-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

#### <a name="details"></a><span data-ttu-id="7dd2b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="7dd2b-102">Details</span></span>

<span data-ttu-id="7dd2b-103">Начиная с .NET Framework 4.5.2 в проектах VB.NET невозможно задать API-интерфейсы System.Windows с частично указанными пространствами имен.</span><span class="sxs-lookup"><span data-stu-id="7dd2b-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="7dd2b-104">Например, ссылка на `Windows.Forms.DialogResult` завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="7dd2b-104">For example, referring to `Windows.Forms.DialogResult` will fail.</span></span> <span data-ttu-id="7dd2b-105">Вместо этого код должен ссылаться на полное доменное имя (<xref:System.Windows.Forms.DialogResult>) или импортировать конкретное пространство имен и сослаться просто на <xref:System.Windows.Forms.DialogResult?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="7dd2b-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7dd2b-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="7dd2b-106">Suggestion</span></span>

<span data-ttu-id="7dd2b-107">Следует обновить код для ссылки на API `System.Windows` либо с простыми именами (и импортом соответствующего пространства имен), либо с полными доменными именами.</span><span class="sxs-lookup"><span data-stu-id="7dd2b-107">Code should be updated to refer to `System.Windows` APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>

| <span data-ttu-id="7dd2b-108">name</span><span class="sxs-lookup"><span data-stu-id="7dd2b-108">Name</span></span>    | <span data-ttu-id="7dd2b-109">Значение</span><span class="sxs-lookup"><span data-stu-id="7dd2b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7dd2b-110">Область</span><span class="sxs-lookup"><span data-stu-id="7dd2b-110">Scope</span></span>   | <span data-ttu-id="7dd2b-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="7dd2b-111">Minor</span></span>       |
| <span data-ttu-id="7dd2b-112">Version</span><span class="sxs-lookup"><span data-stu-id="7dd2b-112">Version</span></span> | <span data-ttu-id="7dd2b-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="7dd2b-113">4.5.2</span></span>       |
| <span data-ttu-id="7dd2b-114">Type</span><span class="sxs-lookup"><span data-stu-id="7dd2b-114">Type</span></span>    | <span data-ttu-id="7dd2b-115">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="7dd2b-115">Retargeting</span></span> |
