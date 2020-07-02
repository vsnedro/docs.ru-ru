---
ms.openlocfilehash: 9659068304eb208fd6a0a753273453bc669fbc56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621403"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="4a6ca-101">Улучшенные подсказки клавиш в WPF</span><span class="sxs-lookup"><span data-stu-id="4a6ca-101">Keytips behavior improved in WPF</span></span>

#### <a name="details"></a><span data-ttu-id="4a6ca-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="4a6ca-102">Details</span></span>

<span data-ttu-id="4a6ca-103">Поведение подсказок клавиш было изменено и теперь совпадает с поведением в проводнике и Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="4a6ca-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="4a6ca-104">WPF проверяет, включено ли состояние подсказки клавиш в случае, если нажата <xref:System.Windows.Input.KeyEventArgs.SystemKey> (в частности, <xref:System.Windows.Input.Key> или <xref:System.Windows.Input.Key.F11>), и обрабатывает клавиши подсказок соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="4a6ca-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="4a6ca-105">Подсказки клавиш теперь закрывают меню, даже если оно открыто с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="4a6ca-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4a6ca-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="4a6ca-106">Suggestion</span></span>

<span data-ttu-id="4a6ca-107">Н/Д</span><span class="sxs-lookup"><span data-stu-id="4a6ca-107">N/A</span></span>

| <span data-ttu-id="4a6ca-108">name</span><span class="sxs-lookup"><span data-stu-id="4a6ca-108">Name</span></span>    | <span data-ttu-id="4a6ca-109">Значение</span><span class="sxs-lookup"><span data-stu-id="4a6ca-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4a6ca-110">Область</span><span class="sxs-lookup"><span data-stu-id="4a6ca-110">Scope</span></span>   |<span data-ttu-id="4a6ca-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="4a6ca-111">Edge</span></span>|
|<span data-ttu-id="4a6ca-112">Version</span><span class="sxs-lookup"><span data-stu-id="4a6ca-112">Version</span></span>|<span data-ttu-id="4a6ca-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="4a6ca-113">4.7.2</span></span>|
|<span data-ttu-id="4a6ca-114">Type</span><span class="sxs-lookup"><span data-stu-id="4a6ca-114">Type</span></span>|<span data-ttu-id="4a6ca-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="4a6ca-115">Runtime</span></span>|
