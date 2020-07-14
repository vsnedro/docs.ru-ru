---
title: Безопасность и поля-массивы с общим доступом только для чтения
description: Узнайте, почему следует избегать использования открытых полей массива только для чтения для определения поведения границ или безопасности приложений.
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
ms.openlocfilehash: 0a6a82c2c88fe61bd34c0accb831f018cf8702fc
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281437"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="7ff3b-103">Безопасность и поля-массивы с общим доступом только для чтения</span><span class="sxs-lookup"><span data-stu-id="7ff3b-103">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="7ff3b-104">Никогда не используйте открытые поля только для чтения из управляемых библиотек, чтобы определить поведение границ или безопасность приложений, поскольку можно изменять открытые поля массива, предназначенные только для чтения.</span><span class="sxs-lookup"><span data-stu-id="7ff3b-104">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ff3b-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="7ff3b-105">Remarks</span></span>  

<span data-ttu-id="7ff3b-106">Некоторые классы .NET включают в себя открытые поля только для чтения, содержащие параметры границ для конкретной платформы.</span><span class="sxs-lookup"><span data-stu-id="7ff3b-106">Some .NET classes include read-only public fields that contain platform-specific boundary parameters.</span></span> <span data-ttu-id="7ff3b-107">Например, <xref:System.IO.Path.InvalidPathChars> поле представляет собой массив, описывающий символы, которые не допускаются в строке пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="7ff3b-107">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span> <span data-ttu-id="7ff3b-108">Многие похожие поля существуют в .NET.</span><span class="sxs-lookup"><span data-stu-id="7ff3b-108">Many similar fields are present throughout .NET.</span></span>  
  
 <span data-ttu-id="7ff3b-109">Значения открытых полей только для чтения <xref:System.IO.Path.InvalidPathChars> , например, могут быть изменены кодом или кодом, который использует домен приложения вашего кода.</span><span class="sxs-lookup"><span data-stu-id="7ff3b-109">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="7ff3b-110">Не следует использовать открытые поля только для чтения, например, для определения поведения приложений в границах.</span><span class="sxs-lookup"><span data-stu-id="7ff3b-110">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="7ff3b-111">В противном случае вредоносный код может изменить определения границ и использовать код непредвиденным образом.</span><span class="sxs-lookup"><span data-stu-id="7ff3b-111">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="7ff3b-112">В версии 2,0 и более поздних .NET Framework следует использовать методы, возвращающие новый массив, вместо использования полей открытого массива.</span><span class="sxs-lookup"><span data-stu-id="7ff3b-112">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="7ff3b-113">Например, вместо использования <xref:System.IO.Path.InvalidPathChars> поля следует использовать <xref:System.IO.Path.GetInvalidPathChars%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="7ff3b-113">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="7ff3b-114">Обратите внимание, что типы .NET Framework не используют открытые поля для внутреннего определения типов границ.</span><span class="sxs-lookup"><span data-stu-id="7ff3b-114">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="7ff3b-115">Вместо этого в .NET Framework используются отдельные закрытые поля.</span><span class="sxs-lookup"><span data-stu-id="7ff3b-115">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="7ff3b-116">Изменение значений этих открытых полей не влияет на поведение типов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7ff3b-116">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff3b-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7ff3b-117">See also</span></span>

- [<span data-ttu-id="7ff3b-118">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="7ff3b-118">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
