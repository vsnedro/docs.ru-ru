---
title: Документирование кода с помощью XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: f391fb909cfe4de8f27afb24d6db389e2c8cdfae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590933"
---
# <a name="document-your-code-with-xml-visual-basic"></a><span data-ttu-id="3880d-102">Документирование кода с помощью XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3880d-102">Document your code with XML (Visual Basic)</span></span>

<span data-ttu-id="3880d-103">В Visual Basic можно документировать код с помощью XML.</span><span class="sxs-lookup"><span data-stu-id="3880d-103">In Visual Basic, you can document your code using XML.</span></span>

## <a name="xml-documentation-comments"></a><span data-ttu-id="3880d-104">Комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="3880d-104">XML documentation comments</span></span>

<span data-ttu-id="3880d-105">Visual Basic предоставляет простой способ автоматического создания XML-документации для проектов.</span><span class="sxs-lookup"><span data-stu-id="3880d-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="3880d-106">Можно автоматически создать XML-схему для типов и членов, а затем предоставить сводные данные, описательную документацию для каждого параметра и другие замечания.</span><span class="sxs-lookup"><span data-stu-id="3880d-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="3880d-107">При соответствующей настройке XML-документация автоматически создается в XML-файл с тем же корневым именем файла, что и у проекта.</span><span class="sxs-lookup"><span data-stu-id="3880d-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same root file name as your project.</span></span> <span data-ttu-id="3880d-108">Дополнительные сведения см. в разделе [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="3880d-108">For more information, see [-doc](../../reference/command-line-compiler/doc.md).</span></span>

<span data-ttu-id="3880d-109">XML-файл можно использовать или иным образом манипулировать как XML.</span><span class="sxs-lookup"><span data-stu-id="3880d-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="3880d-110">Этот файл находится в том же каталоге, что и файл Output. exe или. DLL проекта.</span><span class="sxs-lookup"><span data-stu-id="3880d-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>

<span data-ttu-id="3880d-111">Документация по XML начинается с `'''` .</span><span class="sxs-lookup"><span data-stu-id="3880d-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="3880d-112">Обработка этих комментариев имеет некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="3880d-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="3880d-113">Документация должна представлять собой XML с правильным форматом.</span><span class="sxs-lookup"><span data-stu-id="3880d-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="3880d-114">Если XML сформирован неправильно, создается предупреждение, а файл документации содержит комментарий, в котором говорится, что обнаружена ошибка.</span><span class="sxs-lookup"><span data-stu-id="3880d-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>

- <span data-ttu-id="3880d-115">Разработчики могут создавать собственные наборы тегов.</span><span class="sxs-lookup"><span data-stu-id="3880d-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="3880d-116">Существует рекомендуемый набор тегов (см. раздел [теги комментариев XML](../../language-reference/xmldoc/index.md)).</span><span class="sxs-lookup"><span data-stu-id="3880d-116">There is a recommended set of tags (see [XML Comment Tags](../../language-reference/xmldoc/index.md)).</span></span> <span data-ttu-id="3880d-117">Некоторые рекомендуемые теги имеют особые значения.</span><span class="sxs-lookup"><span data-stu-id="3880d-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="3880d-118">\<param>Тег используется для описания параметров.</span><span class="sxs-lookup"><span data-stu-id="3880d-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="3880d-119">При использовании этого тега компилятор проверяет, что параметр существует и все параметры описаны в документации.</span><span class="sxs-lookup"><span data-stu-id="3880d-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="3880d-120">Если проверка завершается неудачно, компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="3880d-120">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="3880d-121">Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода.</span><span class="sxs-lookup"><span data-stu-id="3880d-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="3880d-122">Компилятор проверяет наличие этого элемента кода.</span><span class="sxs-lookup"><span data-stu-id="3880d-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="3880d-123">Если проверка завершается неудачно, компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="3880d-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="3880d-124">Компилятор также учитывает любые `Imports` инструкции при поиске типа, описанного в `cref` атрибуте.</span><span class="sxs-lookup"><span data-stu-id="3880d-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="3880d-125">Этот \<summary> тег используется технологией IntelliSense в Visual Studio для отображения дополнительных сведений о типе или члене.</span><span class="sxs-lookup"><span data-stu-id="3880d-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>

## <a name="related-sections"></a><span data-ttu-id="3880d-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3880d-126">Related sections</span></span>

<span data-ttu-id="3880d-127">Дополнительные сведения о создании XML-файла с комментариями к документации см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="3880d-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>

- [<span data-ttu-id="3880d-128">-doc</span><span class="sxs-lookup"><span data-stu-id="3880d-128">-doc</span></span>](../../reference/command-line-compiler/doc.md)

- [<span data-ttu-id="3880d-129">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="3880d-129">XML Comment Tags</span></span>](../../language-reference/xmldoc/index.md)

- [<span data-ttu-id="3880d-130">Обработка XML-файла</span><span class="sxs-lookup"><span data-stu-id="3880d-130">Processing the XML File</span></span>](processing-the-xml-file.md)

- [<span data-ttu-id="3880d-131">Практическое руководство. Создание XML-документации</span><span class="sxs-lookup"><span data-stu-id="3880d-131">How to: Create XML Documentation</span></span>](how-to-create-xml-documentation.md)

- [<span data-ttu-id="3880d-132">Средства XML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3880d-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a><span data-ttu-id="3880d-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3880d-133">See also</span></span>

- [<span data-ttu-id="3880d-134">Разработка приложений в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3880d-134">Developing Applications with Visual Basic</span></span>](../../developing-apps/index.md)
- [<span data-ttu-id="3880d-135">Руководство по программированию на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3880d-135">Visual Basic Programming Guide</span></span>](../index.md)
