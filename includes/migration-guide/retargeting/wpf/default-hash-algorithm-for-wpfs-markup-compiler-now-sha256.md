---
ms.openlocfilehash: 4303b177ffe01328965c909a5a3809414fcead91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614930"
---
### <a name="the-default-hash-algorithm-for-wpfs-markup-compiler-is-now-sha256"></a><span data-ttu-id="d97b2-101">Алгоритмом хэширования для компилятора разметки WPF по умолчанию теперь является SHA256</span><span class="sxs-lookup"><span data-stu-id="d97b2-101">The default hash algorithm for WPF's Markup Compiler is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="d97b2-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="d97b2-102">Details</span></span>

<span data-ttu-id="d97b2-103">Компилятор разметки (MarkupCompiler) WPF предоставляет службы компиляции для файлов разметки XAML.</span><span class="sxs-lookup"><span data-stu-id="d97b2-103">The WPF MarkupCompiler provides compilation services for XAML markup files.</span></span>  <span data-ttu-id="d97b2-104">В .NET Framework 4.7.1 и более ранних версиях для вычисления значений контрольной суммы по умолчанию использовался хэш-алгоритм SHA1.</span><span class="sxs-lookup"><span data-stu-id="d97b2-104">In the .NET Framework 4.7.1 and earlier versions, the default hash algorithm used for checksums was SHA1.</span></span> <span data-ttu-id="d97b2-105">С учетом выявленных проблем с безопасностью SHA1, начиная с версии .NET Framework 4.7.2, теперь по умолчанию используется алгоритм SHA256.</span><span class="sxs-lookup"><span data-stu-id="d97b2-105">Due to recent security concerns with SHA1, this default has been changed to SHA256 starting with the .NET Framework 4.7.2.</span></span>  <span data-ttu-id="d97b2-106">Это изменение затрагивает все поколения контрольной суммы для файлов разметки во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="d97b2-106">This change affects all checksum generation for markup files during compilation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d97b2-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="d97b2-107">Suggestion</span></span>

<span data-ttu-id="d97b2-108">Разработчикам приложений, предназначенных для .NET Framework 4.7.2 или более поздних версий, которым требуется вернуться к режиму хэширования SHA1, необходимо установить следующий флаг AppContext.</span><span class="sxs-lookup"><span data-stu-id="d97b2-108">A developer who targets .NET Framework 4.7.2 or greater and wants to revert to SHA1 hashing behavior must set the following AppContext flag.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

<span data-ttu-id="d97b2-109">Разработчикам, которым требуется использовать хэширование SHA256 для версий целевой платформы ниже .NET Framework 4.7.2, необходимо задать следующий флаг AppContext.</span><span class="sxs-lookup"><span data-stu-id="d97b2-109">A developer who wants to utilize SHA256 hashing while targeting a framework version below .NET 4.7.2 must set the below AppContext flag.</span></span>  <span data-ttu-id="d97b2-110">Обратите внимание, что установленная версия .NET Framework должна быть 4.7.2 или выше.</span><span class="sxs-lookup"><span data-stu-id="d97b2-110">Note that the installed version of the .NET Framework must be 4.7.2 or greater.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=false&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="d97b2-111">name</span><span class="sxs-lookup"><span data-stu-id="d97b2-111">Name</span></span>    | <span data-ttu-id="d97b2-112">Значение</span><span class="sxs-lookup"><span data-stu-id="d97b2-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d97b2-113">Область</span><span class="sxs-lookup"><span data-stu-id="d97b2-113">Scope</span></span>   | <span data-ttu-id="d97b2-114">Прозрачный</span><span class="sxs-lookup"><span data-stu-id="d97b2-114">Transparent</span></span> |
| <span data-ttu-id="d97b2-115">Version</span><span class="sxs-lookup"><span data-stu-id="d97b2-115">Version</span></span> | <span data-ttu-id="d97b2-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="d97b2-116">4.7.2</span></span>       |
| <span data-ttu-id="d97b2-117">Type</span><span class="sxs-lookup"><span data-stu-id="d97b2-117">Type</span></span>    | <span data-ttu-id="d97b2-118">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="d97b2-118">Retargeting</span></span> |
