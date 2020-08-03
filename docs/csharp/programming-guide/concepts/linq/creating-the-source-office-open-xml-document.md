---
title: Создание исходного документа в формате Office Open XML (C#)
description: Создайте документ Office Open XML WordprocessingML для использования в учебниках по C#. Для работы с этой статьей требуется Microsoft Office.
ms.date: 07/20/2015
ms.assetid: 653c8cdb-73be-4dc2-927f-924cfb4ed9ed
ms.openlocfilehash: e6d6908ee6560218793454f3871705e74095f543
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103989"
---
# <a name="creating-the-source-office-open-xml-document-c"></a><span data-ttu-id="30028-104">Создание исходного документа в формате Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="30028-104">Creating the Source Office Open XML Document (C#)</span></span>

<span data-ttu-id="30028-105">В этом разделе показано создание документа Office Open XML WordprocessingML, который используется в примерах этого учебника.</span><span class="sxs-lookup"><span data-stu-id="30028-105">This topic shows how to create the Office Open XML WordprocessingML document that the other examples in this tutorial use.</span></span> <span data-ttu-id="30028-106">Если следовать приведенным ниже инструкциям, выходные данные будут соответствовать выходным данным каждого примера.</span><span class="sxs-lookup"><span data-stu-id="30028-106">If you follow these instructions, your output will match the output provided in each example.</span></span>

<span data-ttu-id="30028-107">Тем не менее примеры в этом учебнике работают с любым допустимым документом WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="30028-107">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>

<span data-ttu-id="30028-108">Чтобы создать документ, который используется в этом учебнике, необходимо иметь установленный выпуск 2007 системы Microsoft Office или более поздней версии либо Microsoft Office 2003 с пакетом обеспечения совместимости Microsoft Office для форматов файлов Word, Excel и PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="30028-108">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>

## <a name="creating-the-wordprocessingml-document"></a><span data-ttu-id="30028-109">Создание документа WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="30028-109">Creating the WordprocessingML Document</span></span>

#### <a name="to-create-the-wordprocessingml-document"></a><span data-ttu-id="30028-110">Создание документа WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="30028-110">To create the WordprocessingML document</span></span>

1. <span data-ttu-id="30028-111">Создайте документ Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="30028-111">Create a new Microsoft Word document.</span></span>

2. <span data-ttu-id="30028-112">Вставьте в новый документ следующий текст.</span><span class="sxs-lookup"><span data-stu-id="30028-112">Paste the following text into the new document:</span></span>

    ```text
    Parsing WordprocessingML with LINQ to XML

    The following example prints to the console.

    using System;

    class Program {
        public static void Main(string[] args) {
            Console.WriteLine("Hello World");
        }
    }

    This example produces the following output:

    Hello World
    ```

3. <span data-ttu-id="30028-113">Отформатируйте первую строку стилем «Заголовок 1».</span><span class="sxs-lookup"><span data-stu-id="30028-113">Format the first line with the style "Heading 1".</span></span>

4. <span data-ttu-id="30028-114">Выделите строки, содержащие код C#.</span><span class="sxs-lookup"><span data-stu-id="30028-114">Select the lines that contain the C# code.</span></span> <span data-ttu-id="30028-115">Первая строка начинается с ключевого слова `using`.</span><span class="sxs-lookup"><span data-stu-id="30028-115">The first line starts with the `using` keyword.</span></span> <span data-ttu-id="30028-116">Последняя строка содержит последнюю закрывающую фигурную скобку.</span><span class="sxs-lookup"><span data-stu-id="30028-116">The last line is the last closing brace.</span></span> <span data-ttu-id="30028-117">Отформатируйте эти строки шрифтом courier.</span><span class="sxs-lookup"><span data-stu-id="30028-117">Format the lines with the courier font.</span></span> <span data-ttu-id="30028-118">Создайте из них новый стиль и присвойте ему имя «Code».</span><span class="sxs-lookup"><span data-stu-id="30028-118">Format them with a new style, and name the new style "Code".</span></span>

5. <span data-ttu-id="30028-119">Наконец, выделите всю строку, содержащую выходные данные, и отформатируйте ее стилем `Code`.</span><span class="sxs-lookup"><span data-stu-id="30028-119">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>

6. <span data-ttu-id="30028-120">Сохраните документ с именем SampleDoc.docx.</span><span class="sxs-lookup"><span data-stu-id="30028-120">Save the document, and name it SampleDoc.docx.</span></span>

    > [!NOTE]
    > <span data-ttu-id="30028-121">Если используется Microsoft Word 2003, в раскрывающемся списке **Тип файла** выберите **Документ Word 2007**.</span><span class="sxs-lookup"><span data-stu-id="30028-121">If you are using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>
