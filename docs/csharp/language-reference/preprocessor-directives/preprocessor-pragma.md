---
description: '#pragma. Справочник по C#'
title: '#pragma. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 97d7a786c83a8be21f7fd38873061dba0f9278ae
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137959"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="5fe63-103">#pragma (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5fe63-103">#pragma (C# Reference)</span></span>
<span data-ttu-id="5fe63-104">Директива `#pragma` предоставляет компилятору специальные инструкции для компиляции файла, в котором она появляется.</span><span class="sxs-lookup"><span data-stu-id="5fe63-104">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="5fe63-105">Компилятор должен поддерживать эти инструкции.</span><span class="sxs-lookup"><span data-stu-id="5fe63-105">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="5fe63-106">Другими словами, директиву `#pragma` нельзя использовать для создания настраиваемых инструкций предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="5fe63-106">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="5fe63-107">Компилятор Microsoft C# поддерживает следующие две инструкции `#pragma`:</span><span class="sxs-lookup"><span data-stu-id="5fe63-107">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="5fe63-108">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="5fe63-108">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="5fe63-109">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="5fe63-109">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="5fe63-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5fe63-110">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fe63-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="5fe63-111">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="5fe63-112">Имя распознанной директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="5fe63-112">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="5fe63-113">Аргументы директивы pragma.</span><span class="sxs-lookup"><span data-stu-id="5fe63-113">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fe63-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5fe63-114">See also</span></span>

- [<span data-ttu-id="5fe63-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="5fe63-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5fe63-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5fe63-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5fe63-117">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="5fe63-117">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="5fe63-118">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="5fe63-118">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="5fe63-119">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="5fe63-119">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
