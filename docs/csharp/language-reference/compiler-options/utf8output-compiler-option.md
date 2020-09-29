---
description: -utf8output (параметры компилятора C#)
title: -utf8output (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /utf8output
helpviewer_keywords:
- utf8output compiler option [C#]
- /utf8output compiler option [C#]
- -utf8output compiler option [C#]
ms.assetid: 27ff7381-c281-45d7-b2eb-1ad644b1354e
ms.openlocfilehash: 675782ffef9768e57397e765538924b78a2abcaa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171368"
---
# <a name="-utf8output-c-compiler-options"></a><span data-ttu-id="b8722-103">-utf8output (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="b8722-103">-utf8output (C# Compiler Options)</span></span>

<span data-ttu-id="b8722-104">Параметр **-utf8output** отображает выходные данные компилятора в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b8722-104">The **-utf8output** option displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8722-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8722-105">Syntax</span></span>  
  
```console  
-utf8output  
```  
  
## <a name="remarks"></a><span data-ttu-id="b8722-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="b8722-106">Remarks</span></span>  

 <span data-ttu-id="b8722-107">В некоторых конфигурациях для различных языков выходные данные компилятора некорректно отображаются в консоли.</span><span class="sxs-lookup"><span data-stu-id="b8722-107">In some international configurations, compiler output cannot correctly be displayed in the console.</span></span> <span data-ttu-id="b8722-108">В таких конфигурациях следует использовать параметр **-utf8output** для перенаправления выходных данных компилятора в файл.</span><span class="sxs-lookup"><span data-stu-id="b8722-108">In these configurations, use **-utf8output** and redirect compiler output to a file.</span></span>  
  
 <span data-ttu-id="b8722-109">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="b8722-109">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8722-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b8722-110">See also</span></span>

- [<span data-ttu-id="b8722-111">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="b8722-111">C# Compiler Options</span></span>](./index.md)
