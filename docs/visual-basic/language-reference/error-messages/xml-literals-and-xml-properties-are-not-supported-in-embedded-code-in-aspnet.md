---
title: XML литералы и XML свойства не поддерживаются во встроенном в ASP.NET коде
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: d96386f8495685391203826fea85efba47c44951
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163263"
---
# <a name="bc31200-xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a><span data-ttu-id="f77ff-102">BC31200: XML-литералы и XML-свойства не поддерживаются в внедренном коде в ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f77ff-102">BC31200: XML literals and XML properties are not supported in embedded code within ASP.NET</span></span>

<span data-ttu-id="f77ff-103">XML-литералы и XML-свойства не поддерживаются во внедренном коде в ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f77ff-103">XML literals and XML properties are not supported in embedded code within ASP.NET.</span></span> <span data-ttu-id="f77ff-104">Чтобы использовать функции XML, переместите код в код программной части.</span><span class="sxs-lookup"><span data-stu-id="f77ff-104">To use XML features, move the code to code-behind.</span></span>

 <span data-ttu-id="f77ff-105">XML-литерал или свойство оси XML определяются внутри внедренного кода ( `<%= =>` ) в файле ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f77ff-105">An XML literal or XML axis property is defined within embedded code (`<%= =>`) in an ASP.NET file.</span></span>

 <span data-ttu-id="f77ff-106">**Идентификатор ошибки:** BC31200</span><span class="sxs-lookup"><span data-stu-id="f77ff-106">**Error ID:** BC31200</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="f77ff-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f77ff-107">To correct this error</span></span>

- <span data-ttu-id="f77ff-108">Переместите код, включающий XML-литерал или свойство оси XML, в файл кода программной части ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f77ff-108">Move the code that includes the XML literal or XML axis property to an ASP.NET code-behind file.</span></span>

## <a name="see-also"></a><span data-ttu-id="f77ff-109">См. также</span><span class="sxs-lookup"><span data-stu-id="f77ff-109">See also</span></span>

- [<span data-ttu-id="f77ff-110">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="f77ff-110">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="f77ff-111">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="f77ff-111">XML Axis Properties</span></span>](../xml-axis/index.md)
- [<span data-ttu-id="f77ff-112">XML</span><span class="sxs-lookup"><span data-stu-id="f77ff-112">XML</span></span>](../../programming-guide/language-features/xml/index.md)
