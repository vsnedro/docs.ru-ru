---
title: 'Устранение рисков: реализации пользовательских IMessageFilter.PreFilterMessage'
description: Узнайте о пользовательской реализации IMessageFilter.PreFilterMessage, входящей в приложения Windows Forms, предназначенные для .NET Framework 4.6.1 и более поздних версий.
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
ms.openlocfilehash: 5fe7500d3ed6ff293514495df150a747e7946dda
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475259"
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a><span data-ttu-id="e3983-103">Устранение рисков. Пользовательские реализации IMessageFilter.PreFilterMessage</span><span class="sxs-lookup"><span data-stu-id="e3983-103">Mitigation: Custom IMessageFilter.PreFilterMessage Implementations</span></span>

<span data-ttu-id="e3983-104">В приложениях Windows Forms, нацеленных на .NET Framework старше версии .NET Framework 4.6.1 включительно, пользовательская реализация <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> может безопасно фильтровать сообщения при вызове метода <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>, если реализация <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="e3983-104">In Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1, a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation can safely filter messages when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called if the <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation:</span></span>

- <span data-ttu-id="e3983-105">выполняет одно или оба следующих действия:</span><span class="sxs-lookup"><span data-stu-id="e3983-105">Does one or both of the following:</span></span>

  - <span data-ttu-id="e3983-106">добавляет фильтр сообщений путем вызова метода <xref:System.Windows.Forms.Application.AddMessageFilter%2A>,</span><span class="sxs-lookup"><span data-stu-id="e3983-106">Adds a message filter by calling the <xref:System.Windows.Forms.Application.AddMessageFilter%2A> method.</span></span>

  - <span data-ttu-id="e3983-107">удаляет фильтр сообщений путем вызова метода <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>,</span><span class="sxs-lookup"><span data-stu-id="e3983-107">Removes a message filter by calling the <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> method.</span></span> <span data-ttu-id="e3983-108">метод.</span><span class="sxs-lookup"><span data-stu-id="e3983-108">method.</span></span>

- <span data-ttu-id="e3983-109">**а также** передает сообщения путем вызова метода <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e3983-109">**And** pumps messages by calling the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method.</span></span>

## <a name="impact"></a><span data-ttu-id="e3983-110">Последствия</span><span class="sxs-lookup"><span data-stu-id="e3983-110">Impact</span></span>

<span data-ttu-id="e3983-111">Это изменение затрагивает только приложения Windows Forms, предназначенные для .NET Framework, начиная с версии .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="e3983-111">This change only affects Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>

<span data-ttu-id="e3983-112">В приложениях Windows Forms, которые предназначены для более ранних версий платформы .NET Framework, такие реализации в некоторых случаях создают исключение <xref:System.IndexOutOfRangeException> при вызове метода <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e3983-112">For Windows Forms apps that target previous versions of the .NET Framework, such implementations in some cases throw an <xref:System.IndexOutOfRangeException> exception when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called</span></span>

## <a name="mitigation"></a><span data-ttu-id="e3983-113">Устранение рисков</span><span class="sxs-lookup"><span data-stu-id="e3983-113">Mitigation</span></span>

<span data-ttu-id="e3983-114">Если это изменение нежелательно, его можно отключить для приложений, предназначенных для .NET Framework 4.6.1 или более поздних версий, добавив в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения следующий параметр:</span><span class="sxs-lookup"><span data-stu-id="e3983-114">If this change is undesirable, apps that target the .NET Framework 4.6.1 or a later version can opt out of it by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />
</runtime>
```

<span data-ttu-id="e3983-115">Кроме того, это поведение можно включить для приложений, предназначенных для предыдущих версий .NET Framework, но работающих под управлением .NET Framework 4.6.1 или более поздних версий. Для этого добавьте в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения следующий параметр:</span><span class="sxs-lookup"><span data-stu-id="e3983-115">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 or a later version can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />
</runtime>
```

## <a name="see-also"></a><span data-ttu-id="e3983-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e3983-116">See also</span></span>

- [<span data-ttu-id="e3983-117">Совместимость приложений</span><span class="sxs-lookup"><span data-stu-id="e3983-117">Application compatibility</span></span>](application-compatibility.md)
