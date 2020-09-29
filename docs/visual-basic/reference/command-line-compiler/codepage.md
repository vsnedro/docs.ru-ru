---
title: -codepage
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 769f3586ddef7f430fa96d6101b250a5bbc4e26c
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065740"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="404c1-102">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="404c1-102">-codepage (Visual Basic)</span></span>

<span data-ttu-id="404c1-103">Задает кодовую страницу, используемую для всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="404c1-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="404c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="404c1-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="404c1-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="404c1-105">Arguments</span></span>  
  
|<span data-ttu-id="404c1-106">Термин</span><span class="sxs-lookup"><span data-stu-id="404c1-106">Term</span></span>|<span data-ttu-id="404c1-107">Определение</span><span class="sxs-lookup"><span data-stu-id="404c1-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="404c1-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="404c1-108">Required.</span></span> <span data-ttu-id="404c1-109">Компилятор использует кодовую страницу, указанную `id`, для интерпретации кодировки исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="404c1-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="404c1-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="404c1-110">Remarks</span></span>  

 <span data-ttu-id="404c1-111">Чтобы скомпилировать исходный код, сохраненный в определенной кодировке, можно с помощью параметра `-codepage` указать, какую кодовую страницу следует использовать.</span><span class="sxs-lookup"><span data-stu-id="404c1-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="404c1-112">Параметр `-codepage` применяется ко всем файлам исходного кода, включенным в компиляцию.</span><span class="sxs-lookup"><span data-stu-id="404c1-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="404c1-113">Дополнительные сведения см. в статье [Кодировка символов в .NET Framework](../../../standard/base-types/character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="404c1-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="404c1-114">Параметр `-codepage` не требуется, если файлы исходного кода были сохранены с использованием текущей кодовой страницы ANSI, Юникода или UTF-8 с сигнатурой.</span><span class="sxs-lookup"><span data-stu-id="404c1-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="404c1-115">Visual Studio по умолчанию сохраняет все файлы исходного кода с использованием текущей кодовой страницы ANSI, если пользователь не задает другую кодировку в диалоговом окне **Кодировка**.</span><span class="sxs-lookup"><span data-stu-id="404c1-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="404c1-116">Visual Studio использует диалоговое окно **Кодировка** для открытия файлов исходного кода, сохраненных с использованием другой кодовой страницы.</span><span class="sxs-lookup"><span data-stu-id="404c1-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="404c1-117">Параметр `-codepage` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="404c1-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="404c1-118">См. также</span><span class="sxs-lookup"><span data-stu-id="404c1-118">See also</span></span>

- [<span data-ttu-id="404c1-119">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="404c1-119">Visual Basic Command-Line Compiler</span></span>](index.md)
