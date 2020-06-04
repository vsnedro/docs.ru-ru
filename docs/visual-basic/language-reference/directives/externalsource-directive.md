---
title: '#Директива ExternalSource'
ms.date: 07/20/2015
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
ms.openlocfilehash: e4c7704c32c3a6c73e069d0b7129d5386696b438
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402996"
---
# <a name="externalsource-directive"></a><span data-ttu-id="762e1-102">Директива #ExternalSource</span><span class="sxs-lookup"><span data-stu-id="762e1-102">#ExternalSource Directive</span></span>

<span data-ttu-id="762e1-103">Указывает сопоставление между конкретными строками исходного кода и текстом, внешним по отношению к источнику.</span><span class="sxs-lookup"><span data-stu-id="762e1-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="762e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="762e1-104">Syntax</span></span>  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="762e1-105">Компоненты</span><span class="sxs-lookup"><span data-stu-id="762e1-105">Parts</span></span>  

 `StringLiteral`  
 <span data-ttu-id="762e1-106">Путь к внешнему источнику.</span><span class="sxs-lookup"><span data-stu-id="762e1-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="762e1-107">Номер строки первой строки внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="762e1-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="762e1-108">Строка, в которой возникла ошибка во внешнем источнике.</span><span class="sxs-lookup"><span data-stu-id="762e1-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="762e1-109">Завершает блок `#ExternalSource`.</span><span class="sxs-lookup"><span data-stu-id="762e1-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="762e1-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="762e1-110">Remarks</span></span>  

 <span data-ttu-id="762e1-111">Эта директива используется только компилятором и отладчиком.</span><span class="sxs-lookup"><span data-stu-id="762e1-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="762e1-112">Исходный файл может содержать директивы External Source, которые указывают на сопоставление между конкретными строками кода в исходном файле и внешним по отношению к источнику текстом, например ASPX-файлу.</span><span class="sxs-lookup"><span data-stu-id="762e1-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="762e1-113">Если во время компиляции обнаружены ошибки в указанном исходном коде, они определяются как поступающие из внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="762e1-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="762e1-114">Директивы External Source не влияют на компиляцию и не могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="762e1-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="762e1-115">Они предназначены только для внутреннего использования приложением.</span><span class="sxs-lookup"><span data-stu-id="762e1-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="762e1-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="762e1-116">See also</span></span>

- [<span data-ttu-id="762e1-117">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="762e1-117">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)
