---
title: Преобразования типов
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- changing data types [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
ms.openlocfilehash: ee8700ea757cee9c20e2598de029f54ae33a7114
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090161"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="5cada-102">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5cada-102">Type Conversions in Visual Basic</span></span>

<span data-ttu-id="5cada-103">Процесс изменения значения из одного типа данных на другой тип называется *преобразованием*.</span><span class="sxs-lookup"><span data-stu-id="5cada-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="5cada-104">Преобразования могут *расширяться* или *уменьшаться*в зависимости от объема данных используемых типов.</span><span class="sxs-lookup"><span data-stu-id="5cada-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="5cada-105">Они также являются *неявно* или *explicit*явными в зависимости от синтаксиса в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="5cada-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5cada-106">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="5cada-106">In This Section</span></span>  

 [<span data-ttu-id="5cada-107">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="5cada-107">Widening and Narrowing Conversions</span></span>](widening-and-narrowing-conversions.md)  
 <span data-ttu-id="5cada-108">Описывает преобразования, классифицированные, если целевой тип может содержать данные.</span><span class="sxs-lookup"><span data-stu-id="5cada-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="5cada-109">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="5cada-109">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)  
 <span data-ttu-id="5cada-110">Описывает преобразования, которые классифицируются, независимо от того, выполняет ли Visual Basic их автоматически.</span><span class="sxs-lookup"><span data-stu-id="5cada-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="5cada-111">Преобразования значений между строковыми и другими типами</span><span class="sxs-lookup"><span data-stu-id="5cada-111">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="5cada-112">Описывает преобразование между строками и числовыми `Boolean` значениями, значениями даты и времени.</span><span class="sxs-lookup"><span data-stu-id="5cada-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="5cada-113">Практическое руководство. Преобразование объекта к другому типу в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5cada-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="5cada-114">Показывает, как преобразовать `Object` переменную в любой другой тип данных.</span><span class="sxs-lookup"><span data-stu-id="5cada-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="5cada-115">Преобразования массивов</span><span class="sxs-lookup"><span data-stu-id="5cada-115">Array Conversions</span></span>](array-conversions.md)  
 <span data-ttu-id="5cada-116">Пошаговый процесс преобразования между массивами различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="5cada-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5cada-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="5cada-117">Related Sections</span></span>  

 [<span data-ttu-id="5cada-118">Типы данных</span><span class="sxs-lookup"><span data-stu-id="5cada-118">Data Types</span></span>](index.md)  
 <span data-ttu-id="5cada-119">Вводит Visual Basic типы данных и описывает, как их использовать.</span><span class="sxs-lookup"><span data-stu-id="5cada-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="5cada-120">Типы данных</span><span class="sxs-lookup"><span data-stu-id="5cada-120">Data Types</span></span>](../../../language-reference/data-types/index.md)  
 <span data-ttu-id="5cada-121">Содержит список простейших типов данных, предоставляемых Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5cada-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="5cada-122">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="5cada-122">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)  
 <span data-ttu-id="5cada-123">Обсуждаются некоторые распространенные проблемы, которые могут возникнуть при работе с типами данных.</span><span class="sxs-lookup"><span data-stu-id="5cada-123">Discusses some common problems that can arise when working with data types.</span></span>
