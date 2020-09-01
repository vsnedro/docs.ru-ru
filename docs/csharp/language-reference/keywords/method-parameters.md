---
description: Справочник по C#. Параметры методов
title: Справочник по C#. Параметры методов
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 7090bf1c3df65cf1e65942404f883b49612e7521
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134410"
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="071d8-103">Параметры методов (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="071d8-103">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="071d8-104">Параметры, объявленные для метода без [in](./in-parameter-modifier.md), [ref](./ref.md) или [out](./out-parameter-modifier.md), передаются в вызываемый метод по значению.</span><span class="sxs-lookup"><span data-stu-id="071d8-104">Parameters declared for a method without [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="071d8-105">Это значение может изменяться в методе, однако измененное значение не будет сохраняться при возврате управления вызывающей процедуре.</span><span class="sxs-lookup"><span data-stu-id="071d8-105">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="071d8-106">С помощью ключевого слова параметра метода это поведение можно изменить.</span><span class="sxs-lookup"><span data-stu-id="071d8-106">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="071d8-107">В этом разделе описываются ключевые слова, которые можно использовать при объявлении параметров метода:</span><span class="sxs-lookup"><span data-stu-id="071d8-107">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
- <span data-ttu-id="071d8-108">[params](./params.md) указывает, что этот параметр может принимать переменное количество аргументов.</span><span class="sxs-lookup"><span data-stu-id="071d8-108">[params](./params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
- <span data-ttu-id="071d8-109">[in](./in-parameter-modifier.md) указывает, что этот параметр передается по ссылке, но лишь считывается вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="071d8-109">[in](./in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
- <span data-ttu-id="071d8-110">[ref](./ref.md) указывает, что этот параметр передается по ссылке и может быть считан или записан вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="071d8-110">[ref](./ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
- <span data-ttu-id="071d8-111">[out](./out-parameter-modifier.md) указывает, что этот параметр передается по ссылке и записывается вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="071d8-111">[out](./out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="071d8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="071d8-112">See also</span></span>

- [<span data-ttu-id="071d8-113">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="071d8-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="071d8-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="071d8-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="071d8-115">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="071d8-115">C# Keywords</span></span>](./index.md)
