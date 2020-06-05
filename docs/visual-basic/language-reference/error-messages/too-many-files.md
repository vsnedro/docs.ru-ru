---
title: Слишком много файлов
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: 38d39ad20f350137d714ae5d09db5d2204b83621
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362804"
---
# <a name="too-many-files"></a><span data-ttu-id="5b524-102">Слишком много файлов</span><span class="sxs-lookup"><span data-stu-id="5b524-102">Too many files</span></span>
<span data-ttu-id="5b524-103">В корневом каталоге создано либо больше файлов, чем разрешено операционной системой, либо несколько файлов были открыты, чем указано в файле конфигурации в параметре **Files =** . SYS.</span><span class="sxs-lookup"><span data-stu-id="5b524-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5b524-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="5b524-104">To correct this error</span></span>  
  
1. <span data-ttu-id="5b524-105">Если программа открывает, закрывает или сохраняет файлы в корневом каталоге, измените программу так, чтобы она использовала подкаталог.</span><span class="sxs-lookup"><span data-stu-id="5b524-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2. <span data-ttu-id="5b524-106">Увеличьте число файлов, указанных в параметре **Files =** , в файле конфигурации. SYS и перезагрузить компьютер.</span><span class="sxs-lookup"><span data-stu-id="5b524-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b524-107">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5b524-107">See also</span></span>

- [<span data-ttu-id="5b524-108">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="5b524-108">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
