---
ms.openlocfilehash: f75a652f15be6b0d184db20dc5cd8aafd80539fe
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614909"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a><span data-ttu-id="adf32-101">Действия upbutton и downbutton домена WinForm теперь синхронизированы</span><span class="sxs-lookup"><span data-stu-id="adf32-101">WinForm's Domain upbutton and downbutton actions are in sync now</span></span>

#### <a name="details"></a><span data-ttu-id="adf32-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="adf32-102">Details</span></span>

<span data-ttu-id="adf32-103">В .NET Framework 4.7.1 и предыдущих версиях действие <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> элемента управления <xref:System.Windows.Forms.DomainUpDown> игнорируется, если присутствует текст элемента управления, и разработчику приходится использовать действие <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> для элемента управления перед использованием действия <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="adf32-103">In the .NET Framework 4.7.1 and previous versions the <xref:System.Windows.Forms.DomainUpDown> control's <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action is ignored when control text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before using <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="adf32-104">Начиная с .NET Framework 4.7.2 оба действия, <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> и <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>, работают независимо друг от друга в этом сценарии и остаются синхронизированными.</span><span class="sxs-lookup"><span data-stu-id="adf32-104">Starting with the .NET Framework 4.7.2 both the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> actions work independently in this scenario and remain in sync.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="adf32-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="adf32-105">Suggestion</span></span>

<span data-ttu-id="adf32-106">Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.7.2 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="adf32-106">In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="adf32-107">В приложении эти изменения можно использовать одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="adf32-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="adf32-108">Выполнить повторную компиляцию, чтобы нацелить приложение на .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="adf32-108">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="adf32-109">Это изменение включено по умолчанию для приложений Windows Forms, нацеленных на .NET Framework 4.7.2 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="adf32-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="adf32-110">Для отказа от функций прокрутки предыдущих версий [переключатель AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) добавляется в раздел `<runtime>` файла конфигурации приложения и получает значение `false`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="adf32-110">It opts out of the legacy scrolling behavior by adding the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the `<runtime>` section of the app config file and setting it to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="adf32-111">name</span><span class="sxs-lookup"><span data-stu-id="adf32-111">Name</span></span>    | <span data-ttu-id="adf32-112">Значение</span><span class="sxs-lookup"><span data-stu-id="adf32-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="adf32-113">Область</span><span class="sxs-lookup"><span data-stu-id="adf32-113">Scope</span></span>   | <span data-ttu-id="adf32-114">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="adf32-114">Edge</span></span>        |
| <span data-ttu-id="adf32-115">Version</span><span class="sxs-lookup"><span data-stu-id="adf32-115">Version</span></span> | <span data-ttu-id="adf32-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="adf32-116">4.7.2</span></span>       |
| <span data-ttu-id="adf32-117">Type</span><span class="sxs-lookup"><span data-stu-id="adf32-117">Type</span></span>    | <span data-ttu-id="adf32-118">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="adf32-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="adf32-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="adf32-119">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
