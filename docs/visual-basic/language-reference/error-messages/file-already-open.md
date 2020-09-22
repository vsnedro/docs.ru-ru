---
title: Файл уже открыт
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 97f9e13e6802e793f7c7baf1f03ec51205eb6d42
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874171"
---
# <a name="file-already-open"></a><span data-ttu-id="954ce-102">Файл уже открыт</span><span class="sxs-lookup"><span data-stu-id="954ce-102">File already open</span></span>

<span data-ttu-id="954ce-103">Иногда файл должен быть закрыт, прежде чем `FileOpen` может произойти другая операция.</span><span class="sxs-lookup"><span data-stu-id="954ce-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="954ce-104">Некоторые из возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="954ce-104">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="954ce-105">Операция последовательного режима вывода `FileOpen` была выполнена для уже открытого файла</span><span class="sxs-lookup"><span data-stu-id="954ce-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
- <span data-ttu-id="954ce-106">Оператор ссылается на открытый файл.</span><span class="sxs-lookup"><span data-stu-id="954ce-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="954ce-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="954ce-107">To correct this error</span></span>  
  
1. <span data-ttu-id="954ce-108">Закройте файл перед выполнением инструкции.</span><span class="sxs-lookup"><span data-stu-id="954ce-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="954ce-109">См. также</span><span class="sxs-lookup"><span data-stu-id="954ce-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
