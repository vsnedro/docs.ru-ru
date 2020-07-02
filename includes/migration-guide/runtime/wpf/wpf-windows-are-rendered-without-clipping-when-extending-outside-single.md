---
ms.openlocfilehash: d276e2bbf24c8b2389a0a8078c62c327c3729d50
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621445"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="4652b-101">Окна WPF отображаются без обрезки, если изображение выходит за пределы одного монитора</span><span class="sxs-lookup"><span data-stu-id="4652b-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

#### <a name="details"></a><span data-ttu-id="4652b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="4652b-102">Details</span></span>

<span data-ttu-id="4652b-103">В .NET Framework 4.6 на компьютере под управлением Windows 8 и более поздних версий все содержимое окна выводится без обрезки, если изображение выходит за пределы одного экрана при использовании нескольких мониторов.</span><span class="sxs-lookup"><span data-stu-id="4652b-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="4652b-104">Это отличается от предыдущих версий .NET Framework, где окна WPF обрезались, если выходили за пределы одного экрана.</span><span class="sxs-lookup"><span data-stu-id="4652b-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4652b-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="4652b-105">Suggestion</span></span>

<span data-ttu-id="4652b-106">Это поведение (отсутствие или наличие обрезки) можно задать явным образом с помощью элемента <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> в <code>&lt;appSettings&gt;</code> в файле конфигурации приложения или задав свойство <code>EnableMultiMonitorDisplayClipping</code> при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="4652b-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>

| <span data-ttu-id="4652b-107">name</span><span class="sxs-lookup"><span data-stu-id="4652b-107">Name</span></span>    | <span data-ttu-id="4652b-108">Значение</span><span class="sxs-lookup"><span data-stu-id="4652b-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4652b-109">Область</span><span class="sxs-lookup"><span data-stu-id="4652b-109">Scope</span></span>   |<span data-ttu-id="4652b-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="4652b-110">Minor</span></span>|
|<span data-ttu-id="4652b-111">Version</span><span class="sxs-lookup"><span data-stu-id="4652b-111">Version</span></span>|<span data-ttu-id="4652b-112">4.6</span><span class="sxs-lookup"><span data-stu-id="4652b-112">4.6</span></span>|
|<span data-ttu-id="4652b-113">Type</span><span class="sxs-lookup"><span data-stu-id="4652b-113">Type</span></span>|<span data-ttu-id="4652b-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="4652b-114">Runtime</span></span>|
