---
ms.openlocfilehash: e92fe8364800b1775f0acc31d67aef66a42d0b95
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465894"
---
### <a name="obsolete-properties-on-consoleloggeroptions"></a><span data-ttu-id="05dbd-101">Устаревшие свойства ConsoleLoggerOptions</span><span class="sxs-lookup"><span data-stu-id="05dbd-101">Obsolete properties on ConsoleLoggerOptions</span></span>

<span data-ttu-id="05dbd-102">Тип <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> и некоторые свойства <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="05dbd-102">The <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> type and some properties on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> are now obsolete.</span></span>

#### <a name="change-description"></a><span data-ttu-id="05dbd-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="05dbd-103">Change description</span></span>

<span data-ttu-id="05dbd-104">Начиная с .NET 5.0, тип <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> и несколько свойств <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="05dbd-104">Starting in .NET 5.0, the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> type and several properties on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> are obsolete.</span></span> <span data-ttu-id="05dbd-105">Устаревшие свойства:</span><span class="sxs-lookup"><span data-stu-id="05dbd-105">The obsolete properties are:</span></span>

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>

<span data-ttu-id="05dbd-106">Эти свойства теперь доступны в отдельных новых форматировщиках.</span><span class="sxs-lookup"><span data-stu-id="05dbd-106">With the introduction of new formatters, these properties are now available on the individual formatters.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="05dbd-107">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="05dbd-107">Reason for change</span></span>

<span data-ttu-id="05dbd-108">Свойство <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> является типом перечисления, который не может представлять пользовательский форматировщик.</span><span class="sxs-lookup"><span data-stu-id="05dbd-108">The <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> property is an enumeration type, which cannot represent a custom formatter.</span></span>

<span data-ttu-id="05dbd-109">Остальные свойства были заданы в <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> и применены к обоим встроенным форматам для журналов консоли.</span><span class="sxs-lookup"><span data-stu-id="05dbd-109">The remaining properties were set on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> and applied to both of the built-in formats for console logs.</span></span> <span data-ttu-id="05dbd-110">Но с введением нового API форматировщика будет логичным, если форматирование будет представлено в параметрах, относящихся к форматировщику.</span><span class="sxs-lookup"><span data-stu-id="05dbd-110">However, with the introduction of a new formatter API, it makes more sense for formatting to be represented on the formatter-specific options.</span></span> <span data-ttu-id="05dbd-111">Это изменение обеспечивает лучшее разделение средств ведения журнала и связанных форматировщиков.</span><span class="sxs-lookup"><span data-stu-id="05dbd-111">This change provides better separation between the logger and logger formatters.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="05dbd-112">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="05dbd-112">Version introduced</span></span>

<span data-ttu-id="05dbd-113">5.0, предварительная версия 8</span><span class="sxs-lookup"><span data-stu-id="05dbd-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="05dbd-114">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="05dbd-114">Recommended action</span></span>

- <span data-ttu-id="05dbd-115">Используйте новое свойство <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> вместо свойства <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="05dbd-115">Use the new <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> property in place of the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="05dbd-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="05dbd-116">For example:</span></span>

  ```csharp
  loggingBuilder.AddConsole(options =>
  {
    options.FormatterName = ConsoleFormatterNames.Systemd;
  });
  ```

  <span data-ttu-id="05dbd-117">Есть несколько различий между <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> и <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>:</span><span class="sxs-lookup"><span data-stu-id="05dbd-117">There are several differences between <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> and <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>:</span></span>

  - <span data-ttu-id="05dbd-118"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> имеет только два возможных параметра: `Default` и `Systemd`.</span><span class="sxs-lookup"><span data-stu-id="05dbd-118"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> has only two possible options: `Default` and `Systemd`.</span></span>
  - <span data-ttu-id="05dbd-119"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> не учитывает регистр и может быть любой строкой.</span><span class="sxs-lookup"><span data-stu-id="05dbd-119"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> is case insensitive and can be any string.</span></span> <span data-ttu-id="05dbd-120">Зарезервированные встроенные имена — это `Simple`, `Systemd` и `Json` (.NET 5.0 и выше).</span><span class="sxs-lookup"><span data-stu-id="05dbd-120">The reserved, built-in names are `Simple`, `Systemd`, and `Json` (.NET 5.0 and later).</span></span>
  - <span data-ttu-id="05dbd-121">`"Format": "Systemd"` сопоставляется с `"FormatterName": "Systemd"`.</span><span class="sxs-lookup"><span data-stu-id="05dbd-121">`"Format": "Systemd"` maps to `"FormatterName": "Systemd"`.</span></span>
  - <span data-ttu-id="05dbd-122">`"Format": "Default"` сопоставляется с `"FormatterName": "Simple"`.</span><span class="sxs-lookup"><span data-stu-id="05dbd-122">`"Format": "Default"` maps to `"FormatterName": "Simple"`.</span></span>

- <span data-ttu-id="05dbd-123">Для свойств <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat> и <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> используйте соответствующее свойство в новых типах <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions>или <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions>.</span><span class="sxs-lookup"><span data-stu-id="05dbd-123">For the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat>, and <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> properties, use the corresponding property on the new <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions>, or <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> types instead.</span></span> <span data-ttu-id="05dbd-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="05dbd-124">For example:</span></span>

  ```csharp
  loggingBuilder.AddSimpleConsole(options =>
  {
      options.DisableColors = true;
  });
  ```

<span data-ttu-id="05dbd-125">В следующих двух фрагментах кода JSON показано, как изменяется файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="05dbd-125">The following two JSON snippets show how the configuration file changes.</span></span> <span data-ttu-id="05dbd-126">Старый файл конфигурации:</span><span class="sxs-lookup"><span data-stu-id="05dbd-126">Old configuration file:</span></span>

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "None",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    },

    "Console": {
      "LogLevel": {
        "Default": "Information"
      },
      "Format": "Systemd",
      "IncludeScopes": true,
      "TimestampFormat": "HH:mm:ss",
      "UseUtcTimestamp": true
    }
  },
  "AllowedHosts": "*"
}
```

<span data-ttu-id="05dbd-127">Новый файл конфигурации:</span><span class="sxs-lookup"><span data-stu-id="05dbd-127">New configuration file:</span></span>

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "None",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    },

    "Console": {
      "LogLevel": {
        "Default": "Information"
      },
      "FormatterName": "Systemd",
      "FormatterOptions": {
        "IncludeScopes": true,
        "TimestampFormat": "HH:mm:ss",
        "UseUtcTimestamp": true
      }
    }
  },
  "AllowedHosts": "*"
}
```

#### <a name="category"></a><span data-ttu-id="05dbd-128">Категория</span><span class="sxs-lookup"><span data-stu-id="05dbd-128">Category</span></span>

- <span data-ttu-id="05dbd-129">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="05dbd-129">Core .NET libraries</span></span>
- <span data-ttu-id="05dbd-130">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="05dbd-130">ASP.NET</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="05dbd-131">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="05dbd-131">Affected APIs</span></span>

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=fullName>

<!--

#### Affected APIs

- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format`

-->
