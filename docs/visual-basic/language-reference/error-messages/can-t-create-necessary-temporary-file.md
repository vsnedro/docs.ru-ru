---
title: Не удается создать требуемый временный файл
ms.date: 07/20/2015
f1_keywords:
- vbrID322
ms.assetid: 53617b5b-eb06-4188-b4c2-8607cb9fbc79
ms.openlocfilehash: 1a1464e0ac0d87bf9763efe63f2e09927a157a24
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415431"
---
# <a name="cant-create-necessary-temporary-file"></a><span data-ttu-id="e532c-102">Не удается создать требуемый временный файл</span><span class="sxs-lookup"><span data-stu-id="e532c-102">Can't create necessary temporary file</span></span>
<span data-ttu-id="e532c-103">Либо диск заполнен, содержащий каталог, указанный переменной среды TEMP, либо переменная среды TEMP указывает на недопустимый диск или каталог, предназначенный только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e532c-103">Either the drive is full that contains the directory specified by the TEMP environment variable, or the TEMP environment variable specifies an invalid or read-only drive or directory.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e532c-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e532c-104">To correct this error</span></span>  
  
1. <span data-ttu-id="e532c-105">Удалите файлы с диска, если они заполнены.</span><span class="sxs-lookup"><span data-stu-id="e532c-105">Delete files from the drive, if full.</span></span>  
  
2. <span data-ttu-id="e532c-106">Укажите другой диск в переменной среды TEMP.</span><span class="sxs-lookup"><span data-stu-id="e532c-106">Specify a different drive in the TEMP environment variable.</span></span>  
  
3. <span data-ttu-id="e532c-107">Укажите допустимый диск для переменной среды TEMP.</span><span class="sxs-lookup"><span data-stu-id="e532c-107">Specify a valid drive for the TEMP environment variable.</span></span>  
  
4. <span data-ttu-id="e532c-108">Удалите ограничение "только для чтения" из указанного диска или каталога.</span><span class="sxs-lookup"><span data-stu-id="e532c-108">Remove the read-only restriction from the currently specified drive or directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e532c-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e532c-109">See also</span></span>

- [<span data-ttu-id="e532c-110">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="e532c-110">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
