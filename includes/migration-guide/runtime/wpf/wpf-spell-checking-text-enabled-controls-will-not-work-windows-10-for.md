---
ms.openlocfilehash: 6d7f998cda6326e1f584713576a0aa27b3a68655
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496961"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a><span data-ttu-id="14f3b-101">Проверка орфографии WPF в элементах управления с поддержкой текста не будет работать в Windows 10 для языков, не указанных в списке языков ввода ОС</span><span class="sxs-lookup"><span data-stu-id="14f3b-101">WPF spell checking in text-enabled controls will not work in Windows 10 for languages not in the OS's input language list</span></span>

#### <a name="details"></a><span data-ttu-id="14f3b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="14f3b-102">Details</span></span>

<span data-ttu-id="14f3b-103">В Windows 10 средство проверки орфографии может не работать для элементов управления WPF с поддержкой текста, поскольку возможности проверки орфографии платформы доступны только для языков из списка языков ввода. В Windows 10 при добавлении языка в список доступных клавиатур Windows автоматически загружает и устанавливает соответствующий пакет компонента по запросу (FOD), который предоставляет возможности проверки орфографии.</span><span class="sxs-lookup"><span data-stu-id="14f3b-103">When running on Windows 10, the spell checker may not work for WPF text-enabled controls because platform spell-checking capabilities are available only for languages present in the input languages list.In Windows 10, when a language is added to the list of available keyboards, Windows automatically downloads and installs a corresponding Feature on Demand (FOD) package that provides spell-checking capabilities.</span></span> <span data-ttu-id="14f3b-104">При добавлении языка в список языков ввода проверка орфографии будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="14f3b-104">By adding the language to the input languages list, the spell checker will be supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="14f3b-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="14f3b-105">Suggestion</span></span>

<span data-ttu-id="14f3b-106">Имейте в виду, что язык или текст, проверка которого выполняется, следует добавить как язык ввода, чтобы функция проверки орфографии работала в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="14f3b-106">Be aware that the language or text to be spell-checked must be added as an input language for spell-checking to work in Windows 10.</span></span>

| <span data-ttu-id="14f3b-107">name</span><span class="sxs-lookup"><span data-stu-id="14f3b-107">Name</span></span>    | <span data-ttu-id="14f3b-108">Значение</span><span class="sxs-lookup"><span data-stu-id="14f3b-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="14f3b-109">Область</span><span class="sxs-lookup"><span data-stu-id="14f3b-109">Scope</span></span>   |<span data-ttu-id="14f3b-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="14f3b-110">Edge</span></span>|
|<span data-ttu-id="14f3b-111">Version</span><span class="sxs-lookup"><span data-stu-id="14f3b-111">Version</span></span>|<span data-ttu-id="14f3b-112">4.6</span><span class="sxs-lookup"><span data-stu-id="14f3b-112">4.6</span></span>|
|<span data-ttu-id="14f3b-113">Type</span><span class="sxs-lookup"><span data-stu-id="14f3b-113">Type</span></span>|<span data-ttu-id="14f3b-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="14f3b-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="14f3b-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="14f3b-115">Affected APIs</span></span>

<span data-ttu-id="14f3b-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="14f3b-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
