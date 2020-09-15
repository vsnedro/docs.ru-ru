---
ms.openlocfilehash: 21921156295d89aad04f3197fef9fa322f3c8c87
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614664"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a><span data-ttu-id="5fab4-101">Гарантия использования System.Uri согласованного набора зарезервированных символов</span><span class="sxs-lookup"><span data-stu-id="5fab4-101">Ensure System.Uri uses a consistent reserved character set</span></span>

#### <a name="details"></a><span data-ttu-id="5fab4-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="5fab4-102">Details</span></span>

<span data-ttu-id="5fab4-103">В <xref:System.Uri?displayProperty=fullName> некоторые символы, закодированные процентами, которые иногда декодировались, теперь всегда остаются закодированными.</span><span class="sxs-lookup"><span data-stu-id="5fab4-103">In <xref:System.Uri?displayProperty=fullName>, certain percent-encoded characters that were sometimes decoded are now consistently left encoded.</span></span> <span data-ttu-id="5fab4-104">Это справедливо для свойств и методов, которые получают доступ к компонентам пути, запроса, фрагмента или сведений пользователя URI.</span><span class="sxs-lookup"><span data-stu-id="5fab4-104">This occurs across the properties and methods that access the path, query, fragment, or userinfo components of the URI.</span></span> <span data-ttu-id="5fab4-105">Это поведение изменится, только если выполняются оба указанные ниже условия:</span><span class="sxs-lookup"><span data-stu-id="5fab4-105">The behavior will change only when both of the following are true:</span></span>

- <span data-ttu-id="5fab4-106">URI содержит кодированную форму любого из следующих зарезервированных символов: `:`, `'`, `(`, `)`, `!` или `*`.</span><span class="sxs-lookup"><span data-stu-id="5fab4-106">The URI contains the encoded form of any of the following reserved characters: `:`, `'`, `(`, `)`, `!` or `*`.</span></span>
- <span data-ttu-id="5fab4-107">URI содержит строку в кодировке Юникоде или закодированные незарезервированные символы.</span><span class="sxs-lookup"><span data-stu-id="5fab4-107">The URI contains a Unicode or encoded non-reserved character.</span></span> <span data-ttu-id="5fab4-108">Если выполняются оба приведенных выше условия, закодированные зарезервированные символы остаются закодированными.</span><span class="sxs-lookup"><span data-stu-id="5fab4-108">If both of the above are true, the encoded reserved characters are left encoded.</span></span> <span data-ttu-id="5fab4-109">В предыдущих версиях .NET Framework они декодировались.</span><span class="sxs-lookup"><span data-stu-id="5fab4-109">In previous versions of the .NET Framework, they are decoded.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5fab4-110">Предложение</span><span class="sxs-lookup"><span data-stu-id="5fab4-110">Suggestion</span></span>

<span data-ttu-id="5fab4-111">Для приложений, предназначенных для версий платформы .NET Framework, начиная с 4.7.2, новое поведение декодирования включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5fab4-111">For applications that target versions of .NET Framework starting with 4.7.2, the new decoding behavior is enabled by default.</span></span> <span data-ttu-id="5fab4-112">Если это изменение нежелательно, можно отключить его, добавив следующий переключатель [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел `<runtime>` файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="5fab4-112">If this change is undesirable, you can disable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true" />
</runtime>
```

<span data-ttu-id="5fab4-113">Для приложений, предназначенных для более ранних версий .NET Framework, но выполняемых в версиях начиная с .NET Framework 4.7.2, новое поведение декодирования отключено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5fab4-113">For applications that target earlier versions of the .NET Framework but are running under versions starting with .NET Framework 4.7.2, the new decoding behavior is disabled by default.</span></span> <span data-ttu-id="5fab4-114">Вы можете включить это изменение, добавив следующий параметр [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел `<runtime>` файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="5fab4-114">You can enable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false" />
</runtime>
```

| <span data-ttu-id="5fab4-115">name</span><span class="sxs-lookup"><span data-stu-id="5fab4-115">Name</span></span>    | <span data-ttu-id="5fab4-116">Значение</span><span class="sxs-lookup"><span data-stu-id="5fab4-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5fab4-117">Область</span><span class="sxs-lookup"><span data-stu-id="5fab4-117">Scope</span></span>   | <span data-ttu-id="5fab4-118">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="5fab4-118">Minor</span></span>       |
| <span data-ttu-id="5fab4-119">Version</span><span class="sxs-lookup"><span data-stu-id="5fab4-119">Version</span></span> | <span data-ttu-id="5fab4-120">4.7.2</span><span class="sxs-lookup"><span data-stu-id="5fab4-120">4.7.2</span></span>       |
| <span data-ttu-id="5fab4-121">Type</span><span class="sxs-lookup"><span data-stu-id="5fab4-121">Type</span></span>    | <span data-ttu-id="5fab4-122">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="5fab4-122">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="5fab4-123">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="5fab4-123">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
