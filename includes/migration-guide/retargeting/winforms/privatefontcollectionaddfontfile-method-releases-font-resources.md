---
ms.openlocfilehash: 6ee290f6722480778381376f588e16877894f232
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606520"
---
### <a name="privatefontcollectionaddfontfile-method-releases-font-resources"></a><span data-ttu-id="4a247-101">Метод PrivateFontCollection.AddFontFile освобождает ресурсы шрифтов</span><span class="sxs-lookup"><span data-stu-id="4a247-101">PrivateFontCollection.AddFontFile method releases Font resources</span></span>

#### <a name="details"></a><span data-ttu-id="4a247-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="4a247-102">Details</span></span>

<span data-ttu-id="4a247-103">В .NET Framework 4.7.1 и предыдущих версиях класс <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> не освобождает ресурсы шрифтов GDI + после того, как <xref:System.Drawing.Text.PrivateFontCollection> удаляется для объектов <xref:System.Drawing.Font>, добавляемых в эту коллекцию с помощью метода <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)>.</span><span class="sxs-lookup"><span data-stu-id="4a247-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> class does not release the GDI+ font resources after the <xref:System.Drawing.Text.PrivateFontCollection> is disposed for <xref:System.Drawing.Font> objects that are added to this collection using the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)> method.</span></span> <span data-ttu-id="4a247-104">В платформе .NET Framework 4.7.2 и более поздних версиях класс <xref:System.Drawing.Text.FontCollection.Dispose%2A> освобождает шрифты GDI+, которые были добавлены в коллекцию как файлы.</span><span class="sxs-lookup"><span data-stu-id="4a247-104">In the .NET Framework 4.7.2 and later <xref:System.Drawing.Text.FontCollection.Dispose%2A> releases the GDI+ fonts that were added to the collection as files.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4a247-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="4a247-105">Suggestion</span></span>

<span data-ttu-id="4a247-106">**Как принять или отклонить изменения** Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.7.2 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="4a247-106">**How to opt in or out of these changes** In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="4a247-107">В приложении эти изменения можно использовать одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="4a247-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="4a247-108">Выполнить повторную компиляцию, чтобы нацелить приложение на .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="4a247-108">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="4a247-109">Это изменение включено по умолчанию для приложений Windows Forms, нацеленных на .NET Framework 4.7.2 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="4a247-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="4a247-110">Оно нацелено на .NET Framework 4.7.1 и более ранние версии платформы и позволяет отказаться от функций специальных возможностей предыдущих версий путем добавления [переключателя AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел `<runtime>` файла конфигурации приложения и получения значения `false`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4a247-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the `<runtime>` section of the app.config file and setting it to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Drawing.Text.DoNotRemoveGdiFontsResourcesFromFontCollection=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="4a247-111">В приложениях, предназначенных для .NET Framework 4.7.2 или более поздней версии, где требуется сохранить предыдущие функции, можно выбрать отказ от освобождения шрифта, явно установив этот переключатель AppContext в значение `true`.</span><span class="sxs-lookup"><span data-stu-id="4a247-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to not release font resources by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="4a247-112">name</span><span class="sxs-lookup"><span data-stu-id="4a247-112">Name</span></span>    | <span data-ttu-id="4a247-113">Значение</span><span class="sxs-lookup"><span data-stu-id="4a247-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4a247-114">Область</span><span class="sxs-lookup"><span data-stu-id="4a247-114">Scope</span></span>   | <span data-ttu-id="4a247-115">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="4a247-115">Edge</span></span>        |
| <span data-ttu-id="4a247-116">Version</span><span class="sxs-lookup"><span data-stu-id="4a247-116">Version</span></span> | <span data-ttu-id="4a247-117">4.7.2</span><span class="sxs-lookup"><span data-stu-id="4a247-117">4.7.2</span></span>       |
| <span data-ttu-id="4a247-118">Type</span><span class="sxs-lookup"><span data-stu-id="4a247-118">Type</span></span>    | <span data-ttu-id="4a247-119">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="4a247-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="4a247-120">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="4a247-120">Affected APIs</span></span>

- <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>
- <xref:System.Drawing.Text.FontCollection.Dispose?displayProperty=nameWithType>
