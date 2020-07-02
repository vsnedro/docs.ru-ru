---
ms.openlocfilehash: 67e3ff5000ebd38064ed8a57e4fe561afa31f8d8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614712"
---
### <a name="long-path-support"></a><span data-ttu-id="5a552-101">Поддержка длинных путей</span><span class="sxs-lookup"><span data-stu-id="5a552-101">Long path support</span></span>

#### <a name="details"></a><span data-ttu-id="5a552-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="5a552-102">Details</span></span>

<span data-ttu-id="5a552-103">Начиная с приложений, ориентированных на .NET Framework 4.6.2, поддерживаются длинные пути (до 32 тыс. символов), а ограничение длины пути в 260 символов (или `MAX_PATH`) было удалено. Для приложений, которые перекомпилируются для использования в .NET Framework 4.6.2, кодовые пути, ранее вызывавшие исключение <xref:System.IO.PathTooLongException?displayProperty=fullName>, когда путь превышал 260 символов, теперь будут вызывать исключение <xref:System.IO.PathTooLongException?displayProperty=fullName> только при следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="5a552-103">Starting with apps that target the .NET Framework 4.6.2, long paths (of up to 32K characters) are supported, and the 260-character (or `MAX_PATH`) limitation on path lengths has been removed.For apps that are recompiled to target the .NET Framework 4.6.2, code paths that previously threw a <xref:System.IO.PathTooLongException?displayProperty=fullName> because a path exceeded 260 characters will now throw a <xref:System.IO.PathTooLongException?displayProperty=fullName> only under the following conditions:</span></span>

- <span data-ttu-id="5a552-104">длина пути превышает <xref:System.Int16.MaxValue> (32 767) символов;</span><span class="sxs-lookup"><span data-stu-id="5a552-104">The length of the path is greater than <xref:System.Int16.MaxValue> (32,767) characters.</span></span>
- <span data-ttu-id="5a552-105">операционная система возвращает `COR_E_PATHTOOLONG` или его эквивалент;</span><span class="sxs-lookup"><span data-stu-id="5a552-105">The operating system returns `COR_E_PATHTOOLONG` or its equivalent.</span></span>
<span data-ttu-id="5a552-106">Для приложений, предназначенных для .NET Framework 4.6.1 и более ранних версий, среда выполнения автоматически создает исключение <xref:System.IO.PathTooLongException?displayProperty=fullName>, когда длина пути превышает 260 символов.</span><span class="sxs-lookup"><span data-stu-id="5a552-106">For apps that target the .NET Framework 4.6.1 and earlier versions, the runtime automatically throws a <xref:System.IO.PathTooLongException?displayProperty=fullName> whenever a path exceeds 260 characters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5a552-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="5a552-107">Suggestion</span></span>

<span data-ttu-id="5a552-108">Для приложений, предназначенных для .NET Framework 4.6.2, можно отказаться от поддержки длинного пути, добавив следующую строку в раздел `<runtime>` файла `app.config`:</span><span class="sxs-lookup"><span data-stu-id="5a552-108">For apps that target the .NET Framework 4.6.2, you can opt out of long path support if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />
</runtime>
```

<span data-ttu-id="5a552-109">Для приложений, которые предназначены для более ранних версий .NET Framework, но выполняются в .NET Framework 4.6.2 или более поздней версии, можно включить поддержку длинного пути, добавив следующую строку в раздел `<runtime>` файла `app.config`:</span><span class="sxs-lookup"><span data-stu-id="5a552-109">For apps that target earlier versions of the .NET Framework but run on the .NET Framework 4.6.2 or later, you can opt in to long path support by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />
</runtime>
```

| <span data-ttu-id="5a552-110">name</span><span class="sxs-lookup"><span data-stu-id="5a552-110">Name</span></span>    | <span data-ttu-id="5a552-111">Значение</span><span class="sxs-lookup"><span data-stu-id="5a552-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5a552-112">Область</span><span class="sxs-lookup"><span data-stu-id="5a552-112">Scope</span></span>   | <span data-ttu-id="5a552-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="5a552-113">Minor</span></span>       |
| <span data-ttu-id="5a552-114">Version</span><span class="sxs-lookup"><span data-stu-id="5a552-114">Version</span></span> | <span data-ttu-id="5a552-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="5a552-115">4.6.2</span></span>       |
| <span data-ttu-id="5a552-116">Type</span><span class="sxs-lookup"><span data-stu-id="5a552-116">Type</span></span>    | <span data-ttu-id="5a552-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="5a552-117">Retargeting</span></span> |
