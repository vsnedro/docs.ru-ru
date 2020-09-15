---
ms.openlocfilehash: b88f7d4a17f885b687d99ab9410a56039e176080
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614640"
---
### <a name="calls-to-claimsidentity-constructors"></a><span data-ttu-id="e1b2a-101">Вызовы к конструкторам ClaimsIdentity</span><span class="sxs-lookup"><span data-stu-id="e1b2a-101">Calls to ClaimsIdentity constructors</span></span>

#### <a name="details"></a><span data-ttu-id="e1b2a-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="e1b2a-102">Details</span></span>

<span data-ttu-id="e1b2a-103">Начиная с .NET Framework 4.6.2 конструкторы <xref:System.Security.Claims.ClaimsIdentity> с параметром <xref:System.Security.Principal.IIdentity?displayProperty=fullName> иначе задают свойство <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-103">Starting with the .NET Framework 4.6.2, there is a change in how <xref:System.Security.Claims.ClaimsIdentity> constructors with an <xref:System.Security.Principal.IIdentity?displayProperty=fullName> parameter set the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property.</span></span> <span data-ttu-id="e1b2a-104">Если аргумент <xref:System.Security.Principal.IIdentity?displayProperty=fullName> является объектом <xref:System.Security.Claims.ClaimsIdentity>, а свойство <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> этого объекта <xref:System.Security.Claims.ClaimsIdentity> не равно `null`, свойство <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> присоединяется с помощью метода <xref:System.Security.Claims.ClaimsIdentity.Clone>.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-104">If the <xref:System.Security.Principal.IIdentity?displayProperty=fullName> argument is a <xref:System.Security.Claims.ClaimsIdentity> object, and the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of that <xref:System.Security.Claims.ClaimsIdentity> object is not `null`, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property is attached by using the <xref:System.Security.Claims.ClaimsIdentity.Clone> method.</span></span> <span data-ttu-id="e1b2a-105">В Framework 4.6.1 и более ранних версиях свойство <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> прикреплено как существующая ссылка. В результате этого изменения, начиная с .NET Framework 4.6.2, свойство <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> нового объекта <xref:System.Security.Claims.ClaimsIdentity> не равно свойству <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> аргумента конструктора <xref:System.Security.Principal.IIdentity?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-105">In the Framework 4.6.1 and earlier versions, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property is attached as an existing reference.Because of this change, starting with the .NET Framework 4.6.2, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of the new <xref:System.Security.Claims.ClaimsIdentity> object is not equal to the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of the constructor's <xref:System.Security.Principal.IIdentity?displayProperty=fullName> argument.</span></span> <span data-ttu-id="e1b2a-106">В .NET Framework 4.6.1 и более ранних версиях они равны.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-106">In the .NET Framework 4.6.1 and earlier versions, it is equal.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e1b2a-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="e1b2a-107">Suggestion</span></span>

<span data-ttu-id="e1b2a-108">Если такое поведение нежелательно, можно восстановить прежнее поведение, задав переключателю `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` в файле конфигурации приложения значение `true`.</span><span class="sxs-lookup"><span data-stu-id="e1b2a-108">If this behavior is undesirable, you can restore the previous behavior by setting the `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` switch in your application configuration file to `true`.</span></span> <span data-ttu-id="e1b2a-109">Для этого требуется добавить следующую информацию в раздел `<runtime>` файла web.config:</span><span class="sxs-lookup"><span data-stu-id="e1b2a-109">This requires that you add the following to the `<runtime>` section of your web.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="e1b2a-110">name</span><span class="sxs-lookup"><span data-stu-id="e1b2a-110">Name</span></span>    | <span data-ttu-id="e1b2a-111">Значение</span><span class="sxs-lookup"><span data-stu-id="e1b2a-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e1b2a-112">Область</span><span class="sxs-lookup"><span data-stu-id="e1b2a-112">Scope</span></span>   | <span data-ttu-id="e1b2a-113">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="e1b2a-113">Edge</span></span>        |
| <span data-ttu-id="e1b2a-114">Version</span><span class="sxs-lookup"><span data-stu-id="e1b2a-114">Version</span></span> | <span data-ttu-id="e1b2a-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="e1b2a-115">4.6.2</span></span>       |
| <span data-ttu-id="e1b2a-116">Type</span><span class="sxs-lookup"><span data-stu-id="e1b2a-116">Type</span></span>    | <span data-ttu-id="e1b2a-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="e1b2a-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="e1b2a-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="e1b2a-118">Affected APIs</span></span>

- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity)>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim})>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim},System.String,System.String,System.String)>
