---
title: Оператор Input обнаружил конец файла
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: c0cb0373fb0652e9600ac8651661708414561aca
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873962"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="89155-102">Оператор Input обнаружил конец файла</span><span class="sxs-lookup"><span data-stu-id="89155-102">Input past end of file</span></span>

<span data-ttu-id="89155-103">Либо `Input` инструкция считывает из файла, который является пустым, либо в котором используются все данные, либо вы использовали `EOF` функцию с файлом, открытым для двоичного доступа.</span><span class="sxs-lookup"><span data-stu-id="89155-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="89155-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="89155-104">To correct this error</span></span>  
  
1. <span data-ttu-id="89155-105">Используйте `EOF` функцию непосредственно перед `Input` оператором, чтобы определить конец файла.</span><span class="sxs-lookup"><span data-stu-id="89155-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2. <span data-ttu-id="89155-106">Если файл открыт для двоичного доступа, используйте `Seek` и `Loc` .</span><span class="sxs-lookup"><span data-stu-id="89155-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89155-107">См. также</span><span class="sxs-lookup"><span data-stu-id="89155-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
