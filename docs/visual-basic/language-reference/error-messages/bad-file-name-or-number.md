---
title: Недопустимое имя файла или номер
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: d57a9e78e6ae179d3050e5a92399ca731fa16ba7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874899"
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="d50bb-102">Недопустимое имя файла или номер</span><span class="sxs-lookup"><span data-stu-id="d50bb-102">Bad file name or number</span></span>

<span data-ttu-id="d50bb-103">Произошла ошибка при попытке доступа к указанному файлу.</span><span class="sxs-lookup"><span data-stu-id="d50bb-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="d50bb-104">Среди возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="d50bb-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="d50bb-105">Оператор ссылается на файл с именем или номером файла, который не был указан в `FileOpen` инструкции или был указан в `FileOpen` инструкции, но впоследствии был закрыт.</span><span class="sxs-lookup"><span data-stu-id="d50bb-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
- <span data-ttu-id="d50bb-106">Оператор ссылается на файл с номером, который выходит за пределы диапазона номеров файлов.</span><span class="sxs-lookup"><span data-stu-id="d50bb-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
- <span data-ttu-id="d50bb-107">Оператор ссылается на недопустимое имя файла или номер.</span><span class="sxs-lookup"><span data-stu-id="d50bb-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d50bb-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d50bb-108">To correct this error</span></span>  
  
1. <span data-ttu-id="d50bb-109">Убедитесь, что имя файла указано в `FileOpen` инструкции.</span><span class="sxs-lookup"><span data-stu-id="d50bb-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="d50bb-110">Обратите внимание, что при вызове `FileClose` инструкции без аргументов вы могли случайно закрыть все открытые файлы.</span><span class="sxs-lookup"><span data-stu-id="d50bb-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2. <span data-ttu-id="d50bb-111">Если код создает номера файлов алгоритмически, убедитесь, что числа допустимы.</span><span class="sxs-lookup"><span data-stu-id="d50bb-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3. <span data-ttu-id="d50bb-112">Проверьте имена файлов, чтобы убедиться, что они соответствуют соглашениям об операционной системе.</span><span class="sxs-lookup"><span data-stu-id="d50bb-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d50bb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="d50bb-113">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [<span data-ttu-id="d50bb-114">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d50bb-114">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
