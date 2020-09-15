---
ms.openlocfilehash: 53d74db1a77e62cc64250658281fd3e4706fe494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614633"
---
### <a name="allow-unicode-bidirectional-control-characters-in-uris"></a><span data-ttu-id="08560-101">Разрешить двунаправленные управляющие символы Юникода в URI</span><span class="sxs-lookup"><span data-stu-id="08560-101">Allow Unicode Bidirectional Control Characters in URIs</span></span>

#### <a name="details"></a><span data-ttu-id="08560-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="08560-102">Details</span></span>

<span data-ttu-id="08560-103">Юникод определяет несколько специальных управляющих символов, используемых для указания ориентации текста.</span><span class="sxs-lookup"><span data-stu-id="08560-103">Unicode specifies several special control characters used to specify the orientation of text.</span></span> <span data-ttu-id="08560-104">В предыдущих версиях платформы .NET Framework эти символы ошибочно удалялись из всех URI, даже если были представлены в процентной кодировке.</span><span class="sxs-lookup"><span data-stu-id="08560-104">In previous versions of the .NET Framework, these characters were incorrectly stripped from all URIs even if they were present in their percent-encoded form.</span></span> <span data-ttu-id="08560-105">В целях соблюдения стандарта [RFC 3987](https://tools.ietf.org/html/rfc3987) теперь мы разрешаем эти символы в URI.</span><span class="sxs-lookup"><span data-stu-id="08560-105">In order to better follow [RFC 3987](https://tools.ietf.org/html/rfc3987), we now allow these characters in URIs.</span></span> <span data-ttu-id="08560-106">При обнаружении незакодированных символов в URI выполняется процентное кодирование.</span><span class="sxs-lookup"><span data-stu-id="08560-106">When found unencoded in a URI, they are percent-encoded.</span></span> <span data-ttu-id="08560-107">Символы в процентной кодировке остаются без изменений.</span><span class="sxs-lookup"><span data-stu-id="08560-107">When found percent-encoded they are left as-is.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="08560-108">Предложение</span><span class="sxs-lookup"><span data-stu-id="08560-108">Suggestion</span></span>

<span data-ttu-id="08560-109">Для приложений, предназначенных для версий .NET Framework начиная с 4.7.2, поддержка двунаправленных символов Юникода включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08560-109">For applications that target versions of .NET Framework starting with 4.7.2, support for Unicode bidirectional characters is enabled by default.</span></span> <span data-ttu-id="08560-110">Если это изменение нежелательно, можно отключить его, добавив следующий переключатель [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел `<runtime>` файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="08560-110">If this change is undesirable, you can disable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=true" />
</runtime>
```

<span data-ttu-id="08560-111">Для приложений, предназначенных для более ранних версий .NET Framework, но выполняемых в версиях начиная с .NET Framework 4.7.2, поддержка двунаправленных символов Юникода отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08560-111">For applications that target earlier versions of the .NET Framework but are running under versions starting with .NET Framework 4.7.2, support for Unicode bidirectional characters is disabled by default.</span></span> <span data-ttu-id="08560-112">Вы можете включить это изменение, добавив следующий переключатель [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел `<runtime>` файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="08560-112">You can enable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file::</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=false" />
</runtime>
```

| <span data-ttu-id="08560-113">name</span><span class="sxs-lookup"><span data-stu-id="08560-113">Name</span></span>    | <span data-ttu-id="08560-114">Значение</span><span class="sxs-lookup"><span data-stu-id="08560-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="08560-115">Область</span><span class="sxs-lookup"><span data-stu-id="08560-115">Scope</span></span>   | <span data-ttu-id="08560-116">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="08560-116">Minor</span></span>       |
| <span data-ttu-id="08560-117">Version</span><span class="sxs-lookup"><span data-stu-id="08560-117">Version</span></span> | <span data-ttu-id="08560-118">4.7.2</span><span class="sxs-lookup"><span data-stu-id="08560-118">4.7.2</span></span>       |
| <span data-ttu-id="08560-119">Type</span><span class="sxs-lookup"><span data-stu-id="08560-119">Type</span></span>    | <span data-ttu-id="08560-120">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="08560-120">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="08560-121">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="08560-121">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
