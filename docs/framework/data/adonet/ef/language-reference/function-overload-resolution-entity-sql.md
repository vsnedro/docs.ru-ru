---
title: Разрешение перегрузки функций (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9c648054-3808-4a69-9d3e-98e6a4f9c5ca
ms.openlocfilehash: d37cd9342d1fb3b60d5a2c05d373fb7e71f54b1f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189400"
---
# <a name="function-overload-resolution-entity-sql"></a><span data-ttu-id="e783d-102">Разрешение перегрузки функций (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e783d-102">Function Overload Resolution (Entity SQL)</span></span>

<span data-ttu-id="e783d-103">В данном разделе описывается, каким образом разрешаются функции [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e783d-103">This topic describes how [!INCLUDE[esql](../../../../../../includes/esql-md.md)] functions are resolved.</span></span>  
  
 <span data-ttu-id="e783d-104">С одним именем можно определить более одной функции при условии, что эти функции имеют уникальные сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="e783d-104">More than one function can be defined with the same name, as long as the functions have unique signatures.</span></span>  
  
 <span data-ttu-id="e783d-105">В этом случае для определения, на какие функции ссылается данное выражение, следует применить следующие критерии.</span><span class="sxs-lookup"><span data-stu-id="e783d-105">When this is the case, the following criteria must be applied to determine which function is referenced by a given expression.</span></span> <span data-ttu-id="e783d-106">Эти критерии применяются последовательно.</span><span class="sxs-lookup"><span data-stu-id="e783d-106">These criteria are applied in sequence.</span></span> <span data-ttu-id="e783d-107">Первый критерий, применимый только к одной функции, определяет разрешенную функцию.</span><span class="sxs-lookup"><span data-stu-id="e783d-107">The first criterion that applies only to a single function is the resolved function.</span></span>  
  
1. <span data-ttu-id="e783d-108">**Номер параметра**.</span><span class="sxs-lookup"><span data-stu-id="e783d-108">**Parameter number**.</span></span> <span data-ttu-id="e783d-109">Функция имеет то же число параметров, которое указано в выражении.</span><span class="sxs-lookup"><span data-stu-id="e783d-109">The function has the same number of parameters specified in the expression.</span></span>  
  
2. <span data-ttu-id="e783d-110">**Точное совпадение с типом**.</span><span class="sxs-lookup"><span data-stu-id="e783d-110">**Exact match on type**.</span></span> <span data-ttu-id="e783d-111">Тип каждого аргумента функции точно соответствует типу параметра или является литералом NULL.</span><span class="sxs-lookup"><span data-stu-id="e783d-111">Each argument type of the function exactly matches the parameter type, or is the null literal.</span></span>  
  
3. <span data-ttu-id="e783d-112">**Совпадение с подтипом**.</span><span class="sxs-lookup"><span data-stu-id="e783d-112">**Match on subtype**.</span></span> <span data-ttu-id="e783d-113">Тип каждого аргумента функции точно соответствует подтипу типа параметра или аргумент является литералом NULL.</span><span class="sxs-lookup"><span data-stu-id="e783d-113">Each argument type of the function exactly matches or is a sub-type of the parameter type, or the argument is the null literal.</span></span> <span data-ttu-id="e783d-114">В случае, если несколько функций отличаются только числом требуемых преобразований подтипа, разрешаемой является функция с наименьшим числом преобразований подтипа.</span><span class="sxs-lookup"><span data-stu-id="e783d-114">In the event that several functions differ only in the number of sub-type conversions required, the function with the least number of sub-type conversions is the resolved function.</span></span>  
  
4. <span data-ttu-id="e783d-115">**Совпадение с подтипом или повышением типа**.</span><span class="sxs-lookup"><span data-stu-id="e783d-115">**Match on subtype or type promotion**.</span></span> <span data-ttu-id="e783d-116">Тип каждого аргумента функции точно соответствует, является подтипом или может быть повышен до типа параметра или аргумент является литералом NULL.</span><span class="sxs-lookup"><span data-stu-id="e783d-116">Each argument type of the function exactly matches, is a sub-type of, or can be promoted to the parameter type, or the argument is the null literal.</span></span> <span data-ttu-id="e783d-117">С другой стороны, в случае, если несколько функций отличаются только числом требуемых преобразований и повышений подтипа, то разрешаемой является функция с наименьшим числом преобразований и повышений подтипа.</span><span class="sxs-lookup"><span data-stu-id="e783d-117">Again, in the event that several functions differ only in the number of sub-type conversions and promotions, the function with the least number of sub-type conversions and promotions is the resolved function.</span></span>  
  
 <span data-ttu-id="e783d-118">Если ни один из этих критериев не позволяет выбрать единственную функцию, то выражение вызова функции неоднозначно.</span><span class="sxs-lookup"><span data-stu-id="e783d-118">If none of these criteria result in a single function being selected, the function invocation expression is ambiguous.</span></span>  
  
 <span data-ttu-id="e783d-119">Даже если с помощью этих правил можно извлечь единственную функцию, аргументы могут не соответствовать параметрам.</span><span class="sxs-lookup"><span data-stu-id="e783d-119">Even if a single function can be extracted using these rules, the arguments still might not match the parameters.</span></span> <span data-ttu-id="e783d-120">В этом случае возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="e783d-120">An error is raised in this case.</span></span>  
  
 <span data-ttu-id="e783d-121">Что касается определяемых пользователем функций, то приоритет имеет определение для встроенной функции запроса, даже если существует функция, определенная в модели, с сигнатурой, которая больше подходит для пользовательской функции.</span><span class="sxs-lookup"><span data-stu-id="e783d-121">For user-defined functions, the definition for an inline query function takes precedence even when a model-defined function exists with a signature that is a better match for the user-defined function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e783d-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e783d-122">See also</span></span>

- [<span data-ttu-id="e783d-123">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e783d-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="e783d-124">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e783d-124">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="e783d-125">Функции</span><span class="sxs-lookup"><span data-stu-id="e783d-125">Functions</span></span>](functions-entity-sql.md)
