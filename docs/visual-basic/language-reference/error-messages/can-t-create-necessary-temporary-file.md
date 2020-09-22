---
title: Не удается создать требуемый временный файл
ms.date: 07/20/2015
f1_keywords:
- vbrID322
ms.assetid: 53617b5b-eb06-4188-b4c2-8607cb9fbc79
ms.openlocfilehash: c6d8e471796a0fb745289df8b3d1b156265949ca
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874663"
---
# <a name="cant-create-necessary-temporary-file"></a><span data-ttu-id="cc3d5-102">Не удается создать требуемый временный файл</span><span class="sxs-lookup"><span data-stu-id="cc3d5-102">Can't create necessary temporary file</span></span>

<span data-ttu-id="cc3d5-103">Либо диск заполнен, содержащий каталог, указанный переменной среды TEMP, либо переменная среды TEMP указывает на недопустимый диск или каталог, предназначенный только для чтения.</span><span class="sxs-lookup"><span data-stu-id="cc3d5-103">Either the drive is full that contains the directory specified by the TEMP environment variable, or the TEMP environment variable specifies an invalid or read-only drive or directory.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cc3d5-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="cc3d5-104">To correct this error</span></span>  
  
1. <span data-ttu-id="cc3d5-105">Удалите файлы с диска, если они заполнены.</span><span class="sxs-lookup"><span data-stu-id="cc3d5-105">Delete files from the drive, if full.</span></span>  
  
2. <span data-ttu-id="cc3d5-106">Укажите другой диск в переменной среды TEMP.</span><span class="sxs-lookup"><span data-stu-id="cc3d5-106">Specify a different drive in the TEMP environment variable.</span></span>  
  
3. <span data-ttu-id="cc3d5-107">Укажите допустимый диск для переменной среды TEMP.</span><span class="sxs-lookup"><span data-stu-id="cc3d5-107">Specify a valid drive for the TEMP environment variable.</span></span>  
  
4. <span data-ttu-id="cc3d5-108">Удалите ограничение "только для чтения" из указанного диска или каталога.</span><span class="sxs-lookup"><span data-stu-id="cc3d5-108">Remove the read-only restriction from the currently specified drive or directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc3d5-109">См. также</span><span class="sxs-lookup"><span data-stu-id="cc3d5-109">See also</span></span>

- [<span data-ttu-id="cc3d5-110">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="cc3d5-110">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
