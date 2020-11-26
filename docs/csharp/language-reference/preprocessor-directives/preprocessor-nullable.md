---
description: '#nullable — справочник по C#'
title: '#nullable — справочник по C#'
ms.date: 11/18/2020
f1_keywords:
- '#nullable'
helpviewer_keywords:
- '#nullable directive [C#]'
ms.openlocfilehash: 4c114a09f29769fcc824bcdabdc1d523e33f199d
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099451"
---
# <a name="nullable-c-reference"></a><span data-ttu-id="89a3d-103">nullable (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="89a3d-103">#nullable (C# Reference)</span></span>

<span data-ttu-id="89a3d-104">Директива препроцессора `#nullable` устанавливает контекст с *заметками о допустимости значений NULL* и *контекст с предупреждениями о допустимости значений NULL*.</span><span class="sxs-lookup"><span data-stu-id="89a3d-104">The `#nullable` preprocessor directive sets the *nullable annotation context* and *nullable warning context*.</span></span> <span data-ttu-id="89a3d-105">Эта директива определяет, действуют ли заметки, допускающие значение NULL, и могут ли быть заданы предупреждения о допустимости значений NULL.</span><span class="sxs-lookup"><span data-stu-id="89a3d-105">This directive controls whether nullable annotations have effect, and whether nullability warnings are given.</span></span> <span data-ttu-id="89a3d-106">Каждый контекст либо *отключен*, либо *включен*.</span><span class="sxs-lookup"><span data-stu-id="89a3d-106">Each context is either *disabled* or *enabled*.</span></span>

<span data-ttu-id="89a3d-107">Оба контекста можно указать на уровне проекта (за пределами исходного кода C#).</span><span class="sxs-lookup"><span data-stu-id="89a3d-107">Both contexts can be specified at the project level (outside of C# source code).</span></span> <span data-ttu-id="89a3d-108">Директива `#nullable` управляет контекстами заметок и предупреждений и имеет приоритет над параметрами уровня проекта.</span><span class="sxs-lookup"><span data-stu-id="89a3d-108">The `#nullable` directive controls the annotation and warning contexts and takes precedence over the project-level settings.</span></span> <span data-ttu-id="89a3d-109">Директива задает контексты, которыми управляет, пока другая директива не переопределит ее, или до конца исходного файла.</span><span class="sxs-lookup"><span data-stu-id="89a3d-109">A directive sets the context(s) it controls until another directive overrides it, or until the end of the source file.</span></span>

<span data-ttu-id="89a3d-110">Ниже приведены результаты использования директив:</span><span class="sxs-lookup"><span data-stu-id="89a3d-110">The effect of the directives is as follows:</span></span>

- <span data-ttu-id="89a3d-111">`#nullable disable`: задает контексты с заметками и предупреждениями о допустимости значения NULL в значение *отключено*.</span><span class="sxs-lookup"><span data-stu-id="89a3d-111">`#nullable disable`: Sets the nullable annotation and warning contexts to *disabled*.</span></span>
- <span data-ttu-id="89a3d-112">`#nullable enable`: задает контексты с заметками и предупреждениями о допустимости значения NULL в значение *включено*.</span><span class="sxs-lookup"><span data-stu-id="89a3d-112">`#nullable enable`: Sets the nullable annotation and warning contexts to *enabled*.</span></span>
- <span data-ttu-id="89a3d-113">`#nullable restore`: восстанавливает контексты с заметками и предупреждениями о допустимости значения NULL до параметров проекта.</span><span class="sxs-lookup"><span data-stu-id="89a3d-113">`#nullable restore`: Restores the nullable annotation and warning contexts to project settings.</span></span>
- <span data-ttu-id="89a3d-114">`#nullable disable annotations`: устанавливает контекст с заметками о допустимости значения NULL в режим *отключено*.</span><span class="sxs-lookup"><span data-stu-id="89a3d-114">`#nullable disable annotations`: Sets the nullable annotation context to *disabled*.</span></span>
- <span data-ttu-id="89a3d-115">`#nullable enable annotations`: устанавливает контекст с заметками о допустимости значения NULL в режим *включено*.</span><span class="sxs-lookup"><span data-stu-id="89a3d-115">`#nullable enable annotations`: Sets the nullable annotation context to *enabled*.</span></span>
- <span data-ttu-id="89a3d-116">`#nullable restore annotations`: восстанавливает контексты с заметками о допустимости значения NULL до параметров проекта.</span><span class="sxs-lookup"><span data-stu-id="89a3d-116">`#nullable restore annotations`: Restores the nullable annotation context to project settings.</span></span>
- <span data-ttu-id="89a3d-117">`#nullable disable warnings`: устанавливает контекст с предупреждениями о допустимости значения NULL в режим *отключено*.</span><span class="sxs-lookup"><span data-stu-id="89a3d-117">`#nullable disable warnings`: Sets the nullable warning context to *disabled*.</span></span>
- <span data-ttu-id="89a3d-118">`#nullable enable warnings`: устанавливает контекст с предупреждениями о допустимости значения NULL в режим *включено*.</span><span class="sxs-lookup"><span data-stu-id="89a3d-118">`#nullable enable warnings`: Sets the nullable warning context to *enabled*.</span></span>
- <span data-ttu-id="89a3d-119">`#nullable restore warnings`: восстанавливает контексты с предупреждениями о допустимости значения NULL до параметров проекта.</span><span class="sxs-lookup"><span data-stu-id="89a3d-119">`#nullable restore warnings`: Restores the nullable warning context to project settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="89a3d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="89a3d-120">See also</span></span>

- [<span data-ttu-id="89a3d-121">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="89a3d-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="89a3d-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="89a3d-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="89a3d-123">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="89a3d-123">C# Preprocessor Directives</span></span>](./index.md)
