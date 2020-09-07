---
ms.openlocfilehash: e42bce91afab68e509cb35a8992fa3ca2f096872
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496325"
---
### <a name="wpf-printing-stack-update"></a><span data-ttu-id="c2778-101">Обновления стека печати WPF</span><span class="sxs-lookup"><span data-stu-id="c2778-101">WPF Printing Stack Update</span></span>

#### <a name="details"></a><span data-ttu-id="c2778-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="c2778-102">Details</span></span>

<span data-ttu-id="c2778-103">API-интерфейсы WPF для печати, использующие <xref:System.Printing.PrintQueue?displayProperty=fullName>, теперь вызывают API пакета печати документа Windows вместо устаревшего API печати XPS.</span><span class="sxs-lookup"><span data-stu-id="c2778-103">WPF's Printing APIs using <xref:System.Printing.PrintQueue?displayProperty=fullName> now call Window's Print Document Package API in favor of the now deprecated XPS Print API.</span></span> <span data-ttu-id="c2778-104">Это изменение внесено в целях повышения удобства обслуживания. Ни пользователи, ни разработчики не должны заметить какие-либо изменения в поведении или использовании API.</span><span class="sxs-lookup"><span data-stu-id="c2778-104">The change was made with serviceability in mind; neither users nor developers should see any changes in behavior or API usage.</span></span> <span data-ttu-id="c2778-105">Новый стек печати по умолчанию активируется при работе с обновлением Windows 10 Creators Update.</span><span class="sxs-lookup"><span data-stu-id="c2778-105">The new printing stack is enabled by default when running in Windows 10 Creators Update.</span></span> <span data-ttu-id="c2778-106">Старый стек печати по-прежнему будет работать в предыдущих версиях Windows, как и раньше.</span><span class="sxs-lookup"><span data-stu-id="c2778-106">The old printing stack will still continue to work just as before in older Windows versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c2778-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="c2778-107">Suggestion</span></span>

<span data-ttu-id="c2778-108">Чтобы использовать старый стек в Windows 10 Creators Update, задайте значение <code>UseXpsOMPrinting</code> REG_DWORD в разделе реестра <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> равным <code>1</code>.</span><span class="sxs-lookup"><span data-stu-id="c2778-108">To use the old stack in Windows 10 Creators Update, set the <code>UseXpsOMPrinting</code> REG_DWORD value of the <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> registry key to <code>1</code>.</span></span>

| <span data-ttu-id="c2778-109">Имя</span><span class="sxs-lookup"><span data-stu-id="c2778-109">Name</span></span>    | <span data-ttu-id="c2778-110">Значение</span><span class="sxs-lookup"><span data-stu-id="c2778-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c2778-111">Область</span><span class="sxs-lookup"><span data-stu-id="c2778-111">Scope</span></span>   |<span data-ttu-id="c2778-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="c2778-112">Edge</span></span>|
|<span data-ttu-id="c2778-113">Version</span><span class="sxs-lookup"><span data-stu-id="c2778-113">Version</span></span>|<span data-ttu-id="c2778-114">4.7</span><span class="sxs-lookup"><span data-stu-id="c2778-114">4.7</span></span>|
|<span data-ttu-id="c2778-115">Type</span><span class="sxs-lookup"><span data-stu-id="c2778-115">Type</span></span>|<span data-ttu-id="c2778-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="c2778-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c2778-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="c2778-117">Affected APIs</span></span>

<span data-ttu-id="c2778-118">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="c2778-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
