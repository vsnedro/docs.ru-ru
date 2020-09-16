---
title: Практическое руководство. Вызов API Windows
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 863986e94855e02e9fd04685f7dc3e8e7f7b1cc3
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548069"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="98f32-102">Практическое руководство. Вызов Windows API (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98f32-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="98f32-103">В этом примере определяется и вызывается `MessageBox` функция в user32.dll, а затем в нее передается строка.</span><span class="sxs-lookup"><span data-stu-id="98f32-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98f32-104">Пример</span><span class="sxs-lookup"><span data-stu-id="98f32-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="98f32-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="98f32-105">Compile the code</span></span>  
 <span data-ttu-id="98f32-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="98f32-106">This example requires:</span></span>  
  
- <span data-ttu-id="98f32-107">ссылка на пространство имен <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="98f32-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="98f32-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="98f32-108">Robust Programming</span></span>  
 <span data-ttu-id="98f32-109">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="98f32-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="98f32-110">Метод не является статическим, является абстрактным или был определен ранее.</span><span class="sxs-lookup"><span data-stu-id="98f32-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="98f32-111">Родительский тип является интерфейсом, или длина *имени* или *dllname* равна нулю.</span><span class="sxs-lookup"><span data-stu-id="98f32-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="98f32-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="98f32-112">(<xref:System.ArgumentException>)</span></span>  
  
- <span data-ttu-id="98f32-113">*Имя* или параметр *dllname* имеет значение `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="98f32-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="98f32-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="98f32-114">(<xref:System.ArgumentNullException>)</span></span>  
  
- <span data-ttu-id="98f32-115">Содержащий тип был создан ранее с помощью `CreateType`.</span><span class="sxs-lookup"><span data-stu-id="98f32-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="98f32-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="98f32-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f32-117">См. также</span><span class="sxs-lookup"><span data-stu-id="98f32-117">See also</span></span>

- [<span data-ttu-id="98f32-118">Подробный обзор вызова неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="98f32-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="98f32-119">Примеры вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="98f32-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="98f32-120">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="98f32-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- <span data-ttu-id="98f32-121">[Определение метода с помощью порождаемого отражения](/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="98f32-121">[Defining a Method with Reflection Emit](/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span></span>
- [<span data-ttu-id="98f32-122">Пошаговое руководство. Вызов API Windows</span><span class="sxs-lookup"><span data-stu-id="98f32-122">Walkthrough: Calling Windows APIs</span></span>](walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="98f32-123">COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="98f32-123">COM Interop</span></span>](index.md)
