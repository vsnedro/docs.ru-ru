---
ms.openlocfilehash: f980c8029375074889505a8eb7e8a65aaa8d74e4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614772"
---
### <a name="resgen-refuses-to-load-content-from-the-web"></a><span data-ttu-id="02022-101">Resgen не загружает содержимое из Интернета</span><span class="sxs-lookup"><span data-stu-id="02022-101">Resgen refuses to load content from the web</span></span>

#### <a name="details"></a><span data-ttu-id="02022-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="02022-102">Details</span></span>

<span data-ttu-id="02022-103">Файлы RESX могут содержать входные данные в двоичном формате.</span><span class="sxs-lookup"><span data-stu-id="02022-103">.resx files may contain binary formatted input.</span></span> <span data-ttu-id="02022-104">При попытке использовать Resgen для загрузки файла, скачанного из ненадежного расположения, входные данные по умолчанию не загружаются.</span><span class="sxs-lookup"><span data-stu-id="02022-104">If you attempt to use resgen to load a file that was downloaded from an untrusted location, it will fail to load the input by default.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="02022-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="02022-105">Suggestion</span></span>

<span data-ttu-id="02022-106">Пользователи Resgen, которым нужно загрузить входные данные в двоичном формате из ненадежных расположений, могут либо удалить отметку интернет-источника из входного файла, либо применить неявное согласие. Добавьте следующий параметр реестра, чтобы применить неявное согласие на уровне компьютера: [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;.</span><span class="sxs-lookup"><span data-stu-id="02022-106">Resgen users who require loading binary formatted input from untrusted locations can either remove the mark of the web from the input file or apply the opt-out quirk.Add the following registry setting to apply the machine wide opt-out quirk: [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;</span></span>

| <span data-ttu-id="02022-107">name</span><span class="sxs-lookup"><span data-stu-id="02022-107">Name</span></span>    | <span data-ttu-id="02022-108">Значение</span><span class="sxs-lookup"><span data-stu-id="02022-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="02022-109">Область</span><span class="sxs-lookup"><span data-stu-id="02022-109">Scope</span></span>   | <span data-ttu-id="02022-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="02022-110">Edge</span></span>        |
| <span data-ttu-id="02022-111">Version</span><span class="sxs-lookup"><span data-stu-id="02022-111">Version</span></span> | <span data-ttu-id="02022-112">4.7.2</span><span class="sxs-lookup"><span data-stu-id="02022-112">4.7.2</span></span>       |
| <span data-ttu-id="02022-113">Type</span><span class="sxs-lookup"><span data-stu-id="02022-113">Type</span></span>    | <span data-ttu-id="02022-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="02022-114">Retargeting</span></span> |
