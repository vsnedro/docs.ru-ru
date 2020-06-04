---
title: Практическое руководство. Вызов API Windows
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 2c3bb599b79575180eb2b0ec89453f01901f94c0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396847"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="a43b0-102">Практическое руководство. Вызов Windows API (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a43b0-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="a43b0-103">В этом примере определяется и вызывается `MessageBox` функция в user32. dll, а затем в нее передается строка.</span><span class="sxs-lookup"><span data-stu-id="a43b0-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a43b0-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a43b0-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="a43b0-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a43b0-105">Compile the code</span></span>  
 <span data-ttu-id="a43b0-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="a43b0-106">This example requires:</span></span>  
  
- <span data-ttu-id="a43b0-107">ссылка на пространство имен <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="a43b0-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a43b0-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="a43b0-108">Robust Programming</span></span>  
 <span data-ttu-id="a43b0-109">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="a43b0-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="a43b0-110">Метод не является статическим, является абстрактным или был определен ранее.</span><span class="sxs-lookup"><span data-stu-id="a43b0-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="a43b0-111">Родительский тип является интерфейсом, или длина *имени* или *dllname* равна нулю.</span><span class="sxs-lookup"><span data-stu-id="a43b0-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="a43b0-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="a43b0-112">(<xref:System.ArgumentException>)</span></span>  
  
- <span data-ttu-id="a43b0-113">*Имя* или параметр *dllname* имеет значение `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="a43b0-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="a43b0-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="a43b0-114">(<xref:System.ArgumentNullException>)</span></span>  
  
- <span data-ttu-id="a43b0-115">Содержащий тип был создан ранее с помощью `CreateType`.</span><span class="sxs-lookup"><span data-stu-id="a43b0-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="a43b0-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="a43b0-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a43b0-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a43b0-117">See also</span></span>

- [<span data-ttu-id="a43b0-118">Более подробное рассмотрение вызова неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="a43b0-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="a43b0-119">Примеры вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="a43b0-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="a43b0-120">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="a43b0-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- <span data-ttu-id="a43b0-121">[Определение метода с помощью порождаемого отражения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a43b0-121">[Defining a Method with Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span></span>
- [<span data-ttu-id="a43b0-122">Пошаговое руководство. Вызов API Windows</span><span class="sxs-lookup"><span data-stu-id="a43b0-122">Walkthrough: Calling Windows APIs</span></span>](walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="a43b0-123">COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="a43b0-123">COM Interop</span></span>](index.md)
