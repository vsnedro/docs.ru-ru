---
ms.openlocfilehash: 3bb59ba23214f67100d3a78bb689c941b2d187e6
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506990"
---

<span data-ttu-id="6b1d4-101">При установке пакета .NET может появиться примерно такое сообщение об ошибке: `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`.</span><span class="sxs-lookup"><span data-stu-id="6b1d4-101">While installing the .NET package, you may see an error similar to `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`.</span></span> <span data-ttu-id="6b1d4-102">Эта ошибка может означать, что веб-канал пакета для .NET сейчас обновляется до новой версии пакета и следует повторить попытку позже.</span><span class="sxs-lookup"><span data-stu-id="6b1d4-102">This error could mean that the package feed for .NET is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="6b1d4-103">Во время обновления веб-канал пакета остается недоступным не более 30 минут.</span><span class="sxs-lookup"><span data-stu-id="6b1d4-103">During an upgrade, the package feed shouldn't be unavailable for more than 30 minutes.</span></span> <span data-ttu-id="6b1d4-104">Если вы продолжаете получать эту ошибку через 30 минут, отправьте заявку о проблеме на адрес <https://github.com/dotnet/core/issues>.</span><span class="sxs-lookup"><span data-stu-id="6b1d4-104">If you continually receive this error for more than 30 minutes, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
