---
title: Руководство по программированию на C#. Разделители для тегов в документации
description: Сведения о разделителях для тегов документации. Разделители помогают компилятору определить начало и конец комментария в документации.
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], delimiters
- /** */ delimiters for C# documentation tags
- /// delimiter for C# documentation
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
ms.openlocfilehash: 3191e32b0ff2dbde004abaab0b699cd61fcbb150
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381987"
---
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a><span data-ttu-id="7ace1-104">Руководство по программированию на C#. Разделители для тегов в документации</span><span class="sxs-lookup"><span data-stu-id="7ace1-104">Delimiters for documentation tags (C# programming guide)</span></span>

<span data-ttu-id="7ace1-105">Для создания комментариев в документах XML необходимо использовать разделители, по которым компилятор определяет начало и конец комментария.</span><span class="sxs-lookup"><span data-stu-id="7ace1-105">The use of XML doc comments requires delimiters, which indicate to the compiler where a documentation comment begins and ends.</span></span> <span data-ttu-id="7ace1-106">С тегами в XML-документации можно использовать следующие виды разделителей:</span><span class="sxs-lookup"><span data-stu-id="7ace1-106">You can use the following kinds of delimiters with the XML documentation tags:</span></span>

- `///`

  <span data-ttu-id="7ace1-107">Однострочный разделитель.</span><span class="sxs-lookup"><span data-stu-id="7ace1-107">Single-line delimiter.</span></span> <span data-ttu-id="7ace1-108">Это форма, представленная в примерах документов и используемая в шаблонах проектов C#.</span><span class="sxs-lookup"><span data-stu-id="7ace1-108">This is the form that is shown in documentation examples and used by the C# project templates.</span></span> <span data-ttu-id="7ace1-109">Если после разделителя имеется символ пробела, этот символ не включается в выходные данные XML.</span><span class="sxs-lookup"><span data-stu-id="7ace1-109">If there is a white space character following the delimiter, that character is not included in the XML output.</span></span>

  > [!NOTE]
  > <span data-ttu-id="7ace1-110">Интегрированная среда разработки Visual Studio автоматически вставляет теги `<summary>` и `</summary>` и перемещает курсор в этих тегах после ввода разделителя `///` в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="7ace1-110">The Visual Studio integrated development environment (IDE) automatically inserts the `<summary>` and `</summary>` tags and moves your cursor within these tags after you type the `///` delimiter in the code editor.</span></span> <span data-ttu-id="7ace1-111">Вы можете включить или отключить эту функцию в [диалоговом окне "Параметры"](/visualstudio/ide/reference/options-text-editor-csharp-advanced).</span><span class="sxs-lookup"><span data-stu-id="7ace1-111">You can turn this feature on or off in the [Options dialog box](/visualstudio/ide/reference/options-text-editor-csharp-advanced).</span></span>
  
- `/** */`

  <span data-ttu-id="7ace1-112">Многострочные разделители.</span><span class="sxs-lookup"><span data-stu-id="7ace1-112">Multiline delimiters.</span></span>

  <span data-ttu-id="7ace1-113">При использовании разделителей `/** */` нужно следовать нескольким правилам форматирования:</span><span class="sxs-lookup"><span data-stu-id="7ace1-113">There are some formatting rules to follow when you use the `/** */` delimiters:</span></span>
  
  - <span data-ttu-id="7ace1-114">Строка, содержащая разделитель `/**`, не обрабатывается как комментарий, если оставшаяся ее часть представляет собой пробелы.</span><span class="sxs-lookup"><span data-stu-id="7ace1-114">On the line that contains the `/**` delimiter, if the remainder of the line is white space, the line is not processed for comments.</span></span> <span data-ttu-id="7ace1-115">Если первый знак после разделителя `/**` является пробелом, то этот пробел игнорируется, а оставшаяся часть строки обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="7ace1-115">If the first character after the `/**` delimiter is white space, that white space character is ignored and the rest of the line is processed.</span></span> <span data-ttu-id="7ace1-116">В противном случае весь текст, расположенный в строке после разделителя `/**`, обрабатывается как часть комментария.</span><span class="sxs-lookup"><span data-stu-id="7ace1-116">Otherwise, the entire text of the line after the `/**` delimiter is processed as part of the comment.</span></span>

  - <span data-ttu-id="7ace1-117">Строка, содержащая разделитель `*/`, игнорируется, если перед разделителем `*/` стоят только пробелы.</span><span class="sxs-lookup"><span data-stu-id="7ace1-117">On the line that contains the `*/` delimiter, if there is only white space up to the `*/` delimiter, that line is ignored.</span></span> <span data-ttu-id="7ace1-118">В противном случае текст, расположенный в строке до разделителя `*/`, обрабатывается как часть комментария.</span><span class="sxs-lookup"><span data-stu-id="7ace1-118">Otherwise, the text on the line up to the `*/` delimiter is processed as part of the comment.</span></span>
  
  - <span data-ttu-id="7ace1-119">В начале каждой из строк, расположенных после строки, которая начинается с разделителя `/**`, компилятор выполняет поиск общего шаблона.</span><span class="sxs-lookup"><span data-stu-id="7ace1-119">For the lines after the one that begins with the `/**` delimiter, the compiler looks for a common pattern at the beginning of each line.</span></span> <span data-ttu-id="7ace1-120">Шаблон может включать необязательный пробел и знак звездочки (`*`), после которого следуют необязательные пробелы.</span><span class="sxs-lookup"><span data-stu-id="7ace1-120">The pattern can consist of optional white space and an asterisk (`*`), followed by more optional white space.</span></span> <span data-ttu-id="7ace1-121">Если компилятор находит общий шаблон в начале каждой строки, которая не начинается с разделителя `/**` или `*/`, он игнорирует этот шаблон для каждой строки.</span><span class="sxs-lookup"><span data-stu-id="7ace1-121">If the compiler finds a common pattern at the beginning of each line that does not begin with the `/**` delimiter or the `*/` delimiter, it ignores that pattern for each line.</span></span>

  <span data-ttu-id="7ace1-122">Эти правила показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7ace1-122">The following examples illustrate these rules.</span></span>

  - <span data-ttu-id="7ace1-123">В следующем комментарии обрабатывается только строка, которая начинается с `<summary>`.</span><span class="sxs-lookup"><span data-stu-id="7ace1-123">The only part of the following comment that's processed is the line that begins with `<summary>`.</span></span> <span data-ttu-id="7ace1-124">Формат с тремя тегами позволяет создать точно такие же комментарии.</span><span class="sxs-lookup"><span data-stu-id="7ace1-124">The three tag formats produce the same comments.</span></span>

    ```csharp
    /** <summary>text</summary> */

    /**
    <summary>text</summary>
    */

    /**
     * <summary>text</summary>
    */
    ```

  - <span data-ttu-id="7ace1-125">Компилятор обнаруживает в начале второй и третьей строки общий шаблон " \* ".</span><span class="sxs-lookup"><span data-stu-id="7ace1-125">The compiler identifies a common pattern of " \* " at the beginning of the second and third lines.</span></span> <span data-ttu-id="7ace1-126">Шаблон не включается в выходные данные.</span><span class="sxs-lookup"><span data-stu-id="7ace1-126">The pattern is not included in the output.</span></span>

    ```csharp
    /**
     * <summary>
     * text </summary>*/
    ```

  - <span data-ttu-id="7ace1-127">Компилятор не обнаруживает общий шаблон в следующем комментарии, так как второй знак в третьей строке не является звездочкой.</span><span class="sxs-lookup"><span data-stu-id="7ace1-127">The compiler finds no common pattern in the following comment because the second character on the third line is not an asterisk.</span></span> <span data-ttu-id="7ace1-128">Следовательно, весь текст во второй и третьей строках обрабатывается как часть примечания.</span><span class="sxs-lookup"><span data-stu-id="7ace1-128">Therefore, all text on the second and third lines is processed as part of the comment.</span></span>

    ```csharp
    /**
     * <summary>
       text </summary>
    */
    ```

  - <span data-ttu-id="7ace1-129">Компилятор не обнаруживает шаблон в следующем комментарии по двум причинам.</span><span class="sxs-lookup"><span data-stu-id="7ace1-129">The compiler finds no pattern in the following comment for two reasons.</span></span> <span data-ttu-id="7ace1-130">Во-первых, количество пробелов перед звездочкой не согласовано.</span><span class="sxs-lookup"><span data-stu-id="7ace1-130">First, the number of spaces before the asterisk is not consistent.</span></span> <span data-ttu-id="7ace1-131">Во-вторых, пятая строка начинается с символа табуляции, который отличается от пробелов.</span><span class="sxs-lookup"><span data-stu-id="7ace1-131">Second, the fifth line begins with a tab, which does not match spaces.</span></span> <span data-ttu-id="7ace1-132">Таким образом, весь текст из строк со второй по пятую обрабатывается как часть комментария.</span><span class="sxs-lookup"><span data-stu-id="7ace1-132">Therefore, all text from lines two through five is processed as part of the comment.</span></span>

    <!-- markdownlint-disable MD010 -->
    ```csharp
    /**
      * <summary>
      * text
     *  text2
        *  </summary>
    */
    ```
    <!-- markdownlint-enable MD010 -->

## <a name="see-also"></a><span data-ttu-id="7ace1-133">См. также</span><span class="sxs-lookup"><span data-stu-id="7ace1-133">See also</span></span>

- [<span data-ttu-id="7ace1-134">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7ace1-134">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="7ace1-135">Комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="7ace1-135">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="7ace1-136">-doc (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="7ace1-136">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
