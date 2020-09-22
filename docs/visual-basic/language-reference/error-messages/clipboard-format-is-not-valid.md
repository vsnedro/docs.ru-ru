---
title: Недопустимый формат буфера обмена
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 429d1e120a0044152a358a87663eb09989f45b0e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874595"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="a580f-102">Недопустимый формат буфера обмена</span><span class="sxs-lookup"><span data-stu-id="a580f-102">Clipboard format is not valid</span></span>

<span data-ttu-id="a580f-103">Указанный формат буфера обмена несовместим с выполняемым методом.</span><span class="sxs-lookup"><span data-stu-id="a580f-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="a580f-104">Среди возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="a580f-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="a580f-105">Использование `GetText` метода или буфера обмена `SetText` с форматом буфера обмена, отличным `vbCFText` от или `vbCFLink` .</span><span class="sxs-lookup"><span data-stu-id="a580f-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
- <span data-ttu-id="a580f-106">Использование `GetData` метода или буфера обмена `SetData` с форматом буфера обмена, отличным от `vbCFBitmap` , `vbCFDIB` или `vbCFMetafile` .</span><span class="sxs-lookup"><span data-stu-id="a580f-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
- <span data-ttu-id="a580f-107">Использование `GetData` методов или `SetData` объекта `DataObject` с форматом буфера обмена в диапазоне, зарезервированном Microsoft Windows для зарегистрированных форматов (&HC000-&хфффф), если этот формат буфера обмена не зарегистрирован в Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="a580f-107">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a580f-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="a580f-108">To correct this error</span></span>  
  
- <span data-ttu-id="a580f-109">Удалите недопустимый формат и укажите допустимый.</span><span class="sxs-lookup"><span data-stu-id="a580f-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a580f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a580f-110">See also</span></span>

- [<span data-ttu-id="a580f-111">Буфер обмена: Добавление других форматов</span><span class="sxs-lookup"><span data-stu-id="a580f-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
