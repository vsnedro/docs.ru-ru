---
ms.openlocfilehash: 8c05af045d2d9666b20f36e36c68cc853f906eae
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506877"
---

<span data-ttu-id="673b8-101">При установке пакета .NET может появиться примерно такое сообщение об ошибке: `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`.</span><span class="sxs-lookup"><span data-stu-id="673b8-101">While installing the .NET package, you may see an error similar to `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`.</span></span> <span data-ttu-id="673b8-102">В целом эта ошибка означает, что веб-канал пакета для .NET сейчас обновляется до новой версии пакета и следует повторить попытку позже.</span><span class="sxs-lookup"><span data-stu-id="673b8-102">Generally speaking, this error means that the package feed for .NET is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="673b8-103">При обновлении канал пакета недоступен не более двух часов.</span><span class="sxs-lookup"><span data-stu-id="673b8-103">During an upgrade, the package feed should not be unavailable for more than 2 hours.</span></span> <span data-ttu-id="673b8-104">Если эта ошибка сохраняется более двух часов, сообщите о проблеме по адресу <https://github.com/dotnet/core/issues>.</span><span class="sxs-lookup"><span data-stu-id="673b8-104">If you continually receive this error for more than 2 hours, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
