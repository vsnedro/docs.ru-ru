---
ms.openlocfilehash: c5a061dffa1deb66e1769d6ec70dfa2155ac6a31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615767"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a><span data-ttu-id="ef2e6-101">Был изменен вызов метода CreateDefaultAuthorizationContext с аргументом NULL</span><span class="sxs-lookup"><span data-stu-id="ef2e6-101">Calling CreateDefaultAuthorizationContext with a null argument has changed</span></span>

#### <a name="details"></a><span data-ttu-id="ef2e6-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ef2e6-102">Details</span></span>

<span data-ttu-id="ef2e6-103">В .NET Framework 4.6 изменилась реализация <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName>, возвращаемая вызовом к <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName> с нулевым аргументом authorizationPolicies.</span><span class="sxs-lookup"><span data-stu-id="ef2e6-103">The implementation of the <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName> returned by a call to the <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName> with a null authorizationPolicies argument has changed its implementation in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ef2e6-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="ef2e6-104">Suggestion</span></span>

<span data-ttu-id="ef2e6-105">В редких случаях в приложениях WCF, которые используют настраиваемую проверку подлинности, могут возникать различия в поведении.</span><span class="sxs-lookup"><span data-stu-id="ef2e6-105">In rare cases, WCF apps that use custom authentication may see behavioral differences.</span></span> <span data-ttu-id="ef2e6-106">В таких случаях прежнее поведение можно восстановить двумя способами.</span><span class="sxs-lookup"><span data-stu-id="ef2e6-106">In such cases, the previous behavior can be restored in either of two ways:</span></span>

- <span data-ttu-id="ef2e6-107">Перекомпилируйте приложение для ориентации на версию .NET Framework, предшествующую 4.6.</span><span class="sxs-lookup"><span data-stu-id="ef2e6-107">Recompile your app to target an earlier version of the .NET Framework than 4.6.</span></span> <span data-ttu-id="ef2e6-108">Для служб, размещенных в IIS, используйте элемент `<httpRuntime targetFramework="x.x">` для выбора более ранней версии .NET Framework в качестве целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="ef2e6-108">For IIS-hosted services, use the `<httpRuntime targetFramework="x.x">` element to target an earlier version of the .NET Framework.</span></span>
- <span data-ttu-id="ef2e6-109">Добавьте следующую строку в раздел `<appSettings>` файла app.config.</span><span class="sxs-lookup"><span data-stu-id="ef2e6-109">Add the following line to the `<appSettings>` section of your app.config file:</span></span>

    ```xml
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />
    ```

| <span data-ttu-id="ef2e6-110">name</span><span class="sxs-lookup"><span data-stu-id="ef2e6-110">Name</span></span>    | <span data-ttu-id="ef2e6-111">Значение</span><span class="sxs-lookup"><span data-stu-id="ef2e6-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ef2e6-112">Область</span><span class="sxs-lookup"><span data-stu-id="ef2e6-112">Scope</span></span>   | <span data-ttu-id="ef2e6-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="ef2e6-113">Minor</span></span>       |
| <span data-ttu-id="ef2e6-114">Version</span><span class="sxs-lookup"><span data-stu-id="ef2e6-114">Version</span></span> | <span data-ttu-id="ef2e6-115">4.6</span><span class="sxs-lookup"><span data-stu-id="ef2e6-115">4.6</span></span>         |
| <span data-ttu-id="ef2e6-116">Type</span><span class="sxs-lookup"><span data-stu-id="ef2e6-116">Type</span></span>    | <span data-ttu-id="ef2e6-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="ef2e6-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="ef2e6-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="ef2e6-118">Affected APIs</span></span>

- <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType>
