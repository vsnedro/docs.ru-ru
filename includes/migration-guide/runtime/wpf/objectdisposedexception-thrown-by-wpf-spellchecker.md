---
ms.openlocfilehash: b836b26f3f52e9d0cc78feb764629bd2fa306657
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621833"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="5adc0-101">Исключение ObjectDisposedException, создаваемое средством проверки орфографии WPF</span><span class="sxs-lookup"><span data-stu-id="5adc0-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

#### <a name="details"></a><span data-ttu-id="5adc0-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="5adc0-102">Details</span></span>

<span data-ttu-id="5adc0-103">В некоторых случаях при завершении работы приложений WPF происходит сбой с исключением <xref:System.ObjectDisposedException?displayProperty=fullName>, создаваемым средством проверки орфографии.</span><span class="sxs-lookup"><span data-stu-id="5adc0-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=fullName> thrown by the spellchecker.</span></span> <span data-ttu-id="5adc0-104">Эта ошибка исправлена в WPF .NET Framework 4.7 за счет правильной обработки этого исключения, что позволяет исключить подобное нежелательное поведение приложений.</span><span class="sxs-lookup"><span data-stu-id="5adc0-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="5adc0-105">Следует отметить, что случайные первичные исключения могут по-прежнему наблюдаться в приложениях, выполняемых в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="5adc0-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5adc0-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="5adc0-106">Suggestion</span></span>

<span data-ttu-id="5adc0-107">Выполните обновление до .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="5adc0-107">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="5adc0-108">name</span><span class="sxs-lookup"><span data-stu-id="5adc0-108">Name</span></span>    | <span data-ttu-id="5adc0-109">Значение</span><span class="sxs-lookup"><span data-stu-id="5adc0-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5adc0-110">Область</span><span class="sxs-lookup"><span data-stu-id="5adc0-110">Scope</span></span>   |<span data-ttu-id="5adc0-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="5adc0-111">Edge</span></span>|
|<span data-ttu-id="5adc0-112">Version</span><span class="sxs-lookup"><span data-stu-id="5adc0-112">Version</span></span>|<span data-ttu-id="5adc0-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="5adc0-113">4.6.1</span></span>|
|<span data-ttu-id="5adc0-114">Type</span><span class="sxs-lookup"><span data-stu-id="5adc0-114">Type</span></span>|<span data-ttu-id="5adc0-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="5adc0-115">Runtime</span></span>|
