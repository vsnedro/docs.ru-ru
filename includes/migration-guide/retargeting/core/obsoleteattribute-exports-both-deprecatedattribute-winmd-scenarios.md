---
ms.openlocfilehash: 424e8ff704b888aa3d2c1254ac712da4034f59b8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616117"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a><span data-ttu-id="cf6f4-101">Атрибут ObsoleteAttribute экспортируется как ObsoleteAttribute и DeprecatedAttribute в сценариях WinMD</span><span class="sxs-lookup"><span data-stu-id="cf6f4-101">ObsoleteAttribute exports as both ObsoleteAttribute and DeprecatedAttribute in WinMD scenarios</span></span>

#### <a name="details"></a><span data-ttu-id="cf6f4-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="cf6f4-102">Details</span></span>

<span data-ttu-id="cf6f4-103">При создании библиотеки метаданных Windows (WINMD-файл) атрибут <xref:System.ObsoleteAttribute?displayProperty=fullName> экспортируется как <xref:System.ObsoleteAttribute?displayProperty=fullName> и [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).</span><span class="sxs-lookup"><span data-stu-id="cf6f4-103">When you create a Windows Metadata library (.winmd file), the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute is exported as both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cf6f4-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="cf6f4-104">Suggestion</span></span>

<span data-ttu-id="cf6f4-105">При перекомпиляции существующего исходного кода, использующего атрибут <xref:System.ObsoleteAttribute?displayProperty=fullName>, могут выдаваться предупреждения при использовании кода из C++/CX или JavaScript. Не рекомендуется применять атрибуты <xref:System.ObsoleteAttribute?displayProperty=fullName> и [ Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) в коде в управляемых сборках. Это может привести к предупреждениям сборки.</span><span class="sxs-lookup"><span data-stu-id="cf6f4-105">Recompilation of existing source code that uses the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute may generate warnings when consuming that code from C++/CX or JavaScript.We do not recommend applying both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) to code in managed assemblies; it may result in build warnings.</span></span>

| <span data-ttu-id="cf6f4-106">name</span><span class="sxs-lookup"><span data-stu-id="cf6f4-106">Name</span></span>    | <span data-ttu-id="cf6f4-107">Значение</span><span class="sxs-lookup"><span data-stu-id="cf6f4-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cf6f4-108">Область</span><span class="sxs-lookup"><span data-stu-id="cf6f4-108">Scope</span></span>   | <span data-ttu-id="cf6f4-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="cf6f4-109">Edge</span></span>        |
| <span data-ttu-id="cf6f4-110">Version</span><span class="sxs-lookup"><span data-stu-id="cf6f4-110">Version</span></span> | <span data-ttu-id="cf6f4-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="cf6f4-111">4.5.1</span></span>       |
| <span data-ttu-id="cf6f4-112">Type</span><span class="sxs-lookup"><span data-stu-id="cf6f4-112">Type</span></span>    | <span data-ttu-id="cf6f4-113">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="cf6f4-113">Retargeting</span></span> |
