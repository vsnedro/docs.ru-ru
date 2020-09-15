---
ms.openlocfilehash: f78d15338aa49de5b729aca12964924a0df00ec6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614832"
---
### <a name="improved-accessibility-for-some-net-sdk-tools"></a><span data-ttu-id="43f63-101">Улучшенные специальные возможности для некоторых средств пакета SDK для .NET</span><span class="sxs-lookup"><span data-stu-id="43f63-101">Improved accessibility for some .NET SDK tools</span></span>

#### <a name="details"></a><span data-ttu-id="43f63-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="43f63-102">Details</span></span>

<span data-ttu-id="43f63-103">В пакете SDK .NET Framework 4.7.1 в средствах SvcConfigEditor.exe и SvcTraceViewer.exe были устранены различные проблемы со специальными возможностями.</span><span class="sxs-lookup"><span data-stu-id="43f63-103">In the .NET Framework SDK 4.7.1, the SvcConfigEditor.exe and SvcTraceViewer.exe tools have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="43f63-104">В основном это были незначительные проблемы, например не определялось имя или некорректно реализовывались шаблоны автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="43f63-104">Most of these were small issues like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="43f63-105">Многие пользователи могли не замечать неверные значения, но клиентам, применяющим вспомогательные технологии, такие как средства чтения с экрана, будет проще использовать эти средства пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="43f63-105">While many users wouldn't be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span> <span data-ttu-id="43f63-106">Безусловно, эти исправления влияют на предыдущее поведение, например порядок фокуса клавиатуры. Чтобы получить все исправления специальных возможностей в этих средствах, выполните следующее в файле app.config:</span><span class="sxs-lookup"><span data-stu-id="43f63-106">Certainly, these fixes change some previous behaviors, like keyboard focus order.In order to get all the accessibility fixes in these tools, you can the following to your app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false"/>
</runtime>
```

| <span data-ttu-id="43f63-107">name</span><span class="sxs-lookup"><span data-stu-id="43f63-107">Name</span></span>    | <span data-ttu-id="43f63-108">Значение</span><span class="sxs-lookup"><span data-stu-id="43f63-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="43f63-109">Область</span><span class="sxs-lookup"><span data-stu-id="43f63-109">Scope</span></span>   | <span data-ttu-id="43f63-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="43f63-110">Edge</span></span>        |
| <span data-ttu-id="43f63-111">Version</span><span class="sxs-lookup"><span data-stu-id="43f63-111">Version</span></span> | <span data-ttu-id="43f63-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="43f63-112">4.7.1</span></span>       |
| <span data-ttu-id="43f63-113">Type</span><span class="sxs-lookup"><span data-stu-id="43f63-113">Type</span></span>    | <span data-ttu-id="43f63-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="43f63-114">Retargeting</span></span> |
