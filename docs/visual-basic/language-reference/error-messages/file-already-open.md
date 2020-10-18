---
title: Файл уже открыт
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: ce8f8bf96d7355e45b2df82e8a131472c2ed2367
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162756"
---
# <a name="file-already-open"></a><span data-ttu-id="3de36-102">Файл уже открыт</span><span class="sxs-lookup"><span data-stu-id="3de36-102">File already open</span></span>

<span data-ttu-id="3de36-103">Иногда файл должен быть закрыт, прежде чем `FileOpen` может произойти другая операция.</span><span class="sxs-lookup"><span data-stu-id="3de36-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="3de36-104">Некоторые из возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="3de36-104">Among the possible causes of this error are:</span></span>

- <span data-ttu-id="3de36-105">Операция последовательного режима вывода `FileOpen` была выполнена для уже открытого файла</span><span class="sxs-lookup"><span data-stu-id="3de36-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>

- <span data-ttu-id="3de36-106">Оператор ссылается на открытый файл.</span><span class="sxs-lookup"><span data-stu-id="3de36-106">A statement refers to an open file.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="3de36-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="3de36-107">To correct this error</span></span>

- <span data-ttu-id="3de36-108">Закройте файл перед выполнением инструкции.</span><span class="sxs-lookup"><span data-stu-id="3de36-108">Close the file before executing the statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="3de36-109">См. также</span><span class="sxs-lookup"><span data-stu-id="3de36-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
