---
ms.openlocfilehash: 5e2e8d1ec5d698d1c1649c2a0a1b4b77dbdf4022
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621408"
---
### <a name="wpf-printing-stack-update"></a><span data-ttu-id="1e473-101">Обновления стека печати WPF</span><span class="sxs-lookup"><span data-stu-id="1e473-101">WPF Printing Stack Update</span></span>

#### <a name="details"></a><span data-ttu-id="1e473-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="1e473-102">Details</span></span>

<span data-ttu-id="1e473-103">API-интерфейсы WPF для печати, использующие <xref:System.Printing.PrintQueue?displayProperty=fullName>, теперь вызывают API пакета печати документа Windows вместо устаревшего API печати XPS.</span><span class="sxs-lookup"><span data-stu-id="1e473-103">WPF's Printing APIs using <xref:System.Printing.PrintQueue?displayProperty=fullName> now call Window's Print Document Package API in favor of the now deprecated XPS Print API.</span></span> <span data-ttu-id="1e473-104">Это изменение внесено в целях повышения удобства обслуживания. Ни пользователи, ни разработчики не должны заметить какие-либо изменения в поведении или использовании API.</span><span class="sxs-lookup"><span data-stu-id="1e473-104">The change was made with serviceability in mind; neither users nor developers should see any changes in behavior or API usage.</span></span> <span data-ttu-id="1e473-105">Новый стек печати по умолчанию активируется при работе с обновлением Windows 10 Creators Update.</span><span class="sxs-lookup"><span data-stu-id="1e473-105">The new printing stack is enabled by default when running in Windows 10 Creators Update.</span></span> <span data-ttu-id="1e473-106">Старый стек печати по-прежнему будет работать в предыдущих версиях Windows, как и раньше.</span><span class="sxs-lookup"><span data-stu-id="1e473-106">The old printing stack will still continue to work just as before in older Windows versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1e473-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="1e473-107">Suggestion</span></span>

<span data-ttu-id="1e473-108">Чтобы использовать старый стек в Windows 10 Creators Update, задайте значение <code>UseXpsOMPrinting</code> REG_DWORD в разделе реестра <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> равным <code>1</code>.</span><span class="sxs-lookup"><span data-stu-id="1e473-108">To use the old stack in Windows 10 Creators Update, set the <code>UseXpsOMPrinting</code> REG_DWORD value of the <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> registry key to <code>1</code>.</span></span>

| <span data-ttu-id="1e473-109">name</span><span class="sxs-lookup"><span data-stu-id="1e473-109">Name</span></span>    | <span data-ttu-id="1e473-110">Значение</span><span class="sxs-lookup"><span data-stu-id="1e473-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1e473-111">Область</span><span class="sxs-lookup"><span data-stu-id="1e473-111">Scope</span></span>   |<span data-ttu-id="1e473-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="1e473-112">Edge</span></span>|
|<span data-ttu-id="1e473-113">Version</span><span class="sxs-lookup"><span data-stu-id="1e473-113">Version</span></span>|<span data-ttu-id="1e473-114">4.7</span><span class="sxs-lookup"><span data-stu-id="1e473-114">4.7</span></span>|
|<span data-ttu-id="1e473-115">Type</span><span class="sxs-lookup"><span data-stu-id="1e473-115">Type</span></span>|<span data-ttu-id="1e473-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="1e473-116">Runtime</span></span>|
