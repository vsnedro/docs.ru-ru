---
description: '#pragma. Справочник по C#'
title: '#pragma. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 2788c2589bee149676c5cb2b4212ec7a060a47af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168521"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="885c1-103">#pragma (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="885c1-103">#pragma (C# Reference)</span></span>

<span data-ttu-id="885c1-104">Директива `#pragma` предоставляет компилятору специальные инструкции для компиляции файла, в котором она появляется.</span><span class="sxs-lookup"><span data-stu-id="885c1-104">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="885c1-105">Компилятор должен поддерживать эти инструкции.</span><span class="sxs-lookup"><span data-stu-id="885c1-105">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="885c1-106">Другими словами, директиву `#pragma` нельзя использовать для создания настраиваемых инструкций предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="885c1-106">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="885c1-107">Компилятор Microsoft C# поддерживает следующие две инструкции `#pragma`:</span><span class="sxs-lookup"><span data-stu-id="885c1-107">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="885c1-108">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="885c1-108">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="885c1-109">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="885c1-109">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="885c1-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="885c1-110">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="885c1-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="885c1-111">Parameters</span></span>  

 `pragma-name`  
 <span data-ttu-id="885c1-112">Имя распознанной директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="885c1-112">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="885c1-113">Аргументы директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="885c1-113">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="885c1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="885c1-114">See also</span></span>

- [<span data-ttu-id="885c1-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="885c1-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="885c1-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="885c1-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="885c1-117">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="885c1-117">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="885c1-118">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="885c1-118">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="885c1-119">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="885c1-119">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
