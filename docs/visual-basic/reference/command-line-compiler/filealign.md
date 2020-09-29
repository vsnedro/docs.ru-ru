---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: 809b7ad005b6bb5f127f84425b5d2beb980df471
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058135"
---
# <a name="-filealign"></a><span data-ttu-id="682ce-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="682ce-102">-filealign</span></span>

<span data-ttu-id="682ce-103">Задает выравнивание размеров выходного файла.</span><span class="sxs-lookup"><span data-stu-id="682ce-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="682ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="682ce-104">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="682ce-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="682ce-105">Arguments</span></span>  

 `number`  
 <span data-ttu-id="682ce-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="682ce-106">Required.</span></span> <span data-ttu-id="682ce-107">Значение, которое определяет выравнивание разделов в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="682ce-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="682ce-108">Допустимые значения: 512, 1024, 2048, 4096 и 8192.</span><span class="sxs-lookup"><span data-stu-id="682ce-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="682ce-109">Эти значения указаны в байтах.</span><span class="sxs-lookup"><span data-stu-id="682ce-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="682ce-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="682ce-110">Remarks</span></span>  

 <span data-ttu-id="682ce-111">Можно использовать параметр `-filealign`, чтобы определить выравнивание разделов в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="682ce-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="682ce-112">Разделы — это блоки непрерывной памяти в PE-файле, содержащем код или данные.</span><span class="sxs-lookup"><span data-stu-id="682ce-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="682ce-113">Параметр `-filealign` позволяет компилировать приложение с нестандартным выравниванием. Большинству разработчиков не нужно использовать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="682ce-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="682ce-114">Каждый раздел выравнивается по границе, кратной значению `-filealign`.</span><span class="sxs-lookup"><span data-stu-id="682ce-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="682ce-115">Фиксированный размер по умолчанию не предусмотрен.</span><span class="sxs-lookup"><span data-stu-id="682ce-115">There is no fixed default.</span></span> <span data-ttu-id="682ce-116">Если не указать `-filealign`, компилятор выбирает значение по умолчанию во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="682ce-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="682ce-117">Определив размер раздела, можно изменить размер выходного файла.</span><span class="sxs-lookup"><span data-stu-id="682ce-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="682ce-118">Изменение размера раздела может применяться для программ, выполняющихся на небольших устройствах.</span><span class="sxs-lookup"><span data-stu-id="682ce-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="682ce-119">Параметр `-filealign` недоступен в среде разработки Visual Studio. Он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="682ce-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="682ce-120">См. также</span><span class="sxs-lookup"><span data-stu-id="682ce-120">See also</span></span>

- [<span data-ttu-id="682ce-121">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="682ce-121">Visual Basic Command-Line Compiler</span></span>](index.md)
