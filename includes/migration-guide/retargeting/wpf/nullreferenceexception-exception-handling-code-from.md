---
ms.openlocfilehash: 9c9c4ec55143ef991e9b69a389e0f3368263bb4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614846"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a><span data-ttu-id="add51-101">NullReferenceException в коде обработки исключений из ImageSourceConverter.ConvertFrom</span><span class="sxs-lookup"><span data-stu-id="add51-101">NullReferenceException in exception handling code from ImageSourceConverter.ConvertFrom</span></span>

#### <a name="details"></a><span data-ttu-id="add51-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="add51-102">Details</span></span>

<span data-ttu-id="add51-103">Ошибка в коде обработки исключений для <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> вызывала некорректное исключение <xref:System.NullReferenceException?displayProperty=fullName> вместо предполагаемого исключения (<xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> или <xref:System.IO.FileNotFoundException?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="add51-103">An error in the exception handling code for <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> caused an incorrect <xref:System.NullReferenceException?displayProperty=fullName> to be thrown instead of the intended exception ( <xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> or <xref:System.IO.FileNotFoundException?displayProperty=fullName>).</span></span> <span data-ttu-id="add51-104">Это изменение устраняет эту ошибку. Теперь метод вызывает правильное исключение.</span><span class="sxs-lookup"><span data-stu-id="add51-104">This change corrects that error so that the method now throws the right exception.</span></span> <p/><span data-ttu-id="add51-105">По умолчанию все приложения, предназначенные для .NET Framework 4.6.2 и более ранних версий, по-прежнему вызывают исключение <xref:System.NullReferenceException?displayProperty=fullName> для обеспечения совместимости.</span><span class="sxs-lookup"><span data-stu-id="add51-105">By default all applications targeting .NET Framework 4.6.2 and earlier continue to throw <xref:System.NullReferenceException?displayProperty=fullName> for compatibility.</span></span> <span data-ttu-id="add51-106">Разработчики приложений, предназначенных для .NET Framework 4.7 и более поздних версий, должны видеть правильные исключения.</span><span class="sxs-lookup"><span data-stu-id="add51-106">Developers targeting .NET Framework 4.7 and above should see the right exceptions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="add51-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="add51-107">Suggestion</span></span>

<span data-ttu-id="add51-108">Разработчики, желающие по-прежнему получать <xref:System.NullReferenceException?displayProperty=fullName> при работе с .NET Framework 4.7 и более поздних версий, могут добавить следующее в файл App.config приложения:</span><span class="sxs-lookup"><span data-stu-id="add51-108">Developers who wish to revert to getting <xref:System.NullReferenceException?displayProperty=fullName> when targeting .NET Framework 4.7 or later can add/merge the following to their application's App.config file:</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="add51-109">name</span><span class="sxs-lookup"><span data-stu-id="add51-109">Name</span></span>    | <span data-ttu-id="add51-110">Значение</span><span class="sxs-lookup"><span data-stu-id="add51-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="add51-111">Область</span><span class="sxs-lookup"><span data-stu-id="add51-111">Scope</span></span>   | <span data-ttu-id="add51-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="add51-112">Edge</span></span>        |
| <span data-ttu-id="add51-113">Version</span><span class="sxs-lookup"><span data-stu-id="add51-113">Version</span></span> | <span data-ttu-id="add51-114">4.7</span><span class="sxs-lookup"><span data-stu-id="add51-114">4.7</span></span>         |
| <span data-ttu-id="add51-115">Type</span><span class="sxs-lookup"><span data-stu-id="add51-115">Type</span></span>    | <span data-ttu-id="add51-116">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="add51-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="add51-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="add51-117">Affected APIs</span></span>

- <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType>
