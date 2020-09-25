---
title: Типизированные наборы данных
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 4648d49b1d7419d61a3a000404f42e0d02d25786
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198452"
---
# <a name="typed-datasets"></a><span data-ttu-id="e5411-102">Типизированные наборы данных</span><span class="sxs-lookup"><span data-stu-id="e5411-102">Typed DataSets</span></span>

<span data-ttu-id="e5411-103">Наряду с доступом к значениям с поздним связыванием через слабо типизированные переменные, в объекте <xref:System.Data.DataSet> предоставляется доступ к данным на основе принципа строгой типизации.</span><span class="sxs-lookup"><span data-stu-id="e5411-103">Along with late bound access to values through weakly typed variables, the <xref:System.Data.DataSet> provides access to data through a strongly typed metaphor.</span></span> <span data-ttu-id="e5411-104">Доступ к таблицам и столбцам, которые являются частью **набора данных** , можно получить с помощью понятных имен и строго типизированных переменных.</span><span class="sxs-lookup"><span data-stu-id="e5411-104">Tables and columns that are part of the **DataSet** can be accessed using user-friendly names and strongly typed variables.</span></span>  
  
 <span data-ttu-id="e5411-105">Типизированный **набор данных** — это класс, производный от **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="e5411-105">A typed **DataSet** is a class that derives from a **DataSet**.</span></span> <span data-ttu-id="e5411-106">Таким образом, он наследует все методы, события и свойства **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="e5411-106">As such, it inherits all the methods, events, and properties of a **DataSet**.</span></span> <span data-ttu-id="e5411-107">Кроме того, типизированный **набор данных** предоставляет строго типизированные методы, события и свойства.</span><span class="sxs-lookup"><span data-stu-id="e5411-107">Additionally, a typed **DataSet** provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="e5411-108">Это означает, что к таблицам и столбцам можно обращаться путем указания имен вместо использования методов на основе коллекций.</span><span class="sxs-lookup"><span data-stu-id="e5411-108">This means you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="e5411-109">Помимо улучшенной удобочитаемости кода, типизированный **набор данных** также позволяет редактору кода Visual Studio .NET автоматически завершать строки по мере ввода.</span><span class="sxs-lookup"><span data-stu-id="e5411-109">Aside from the improved readability of the code, a typed **DataSet** also allows the Visual Studio .NET code editor to automatically complete lines as you type.</span></span>  
  
 <span data-ttu-id="e5411-110">Кроме того, строго типизированный **набор данных** предоставляет доступ к значениям в качестве правильного типа во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="e5411-110">Additionally, the strongly typed **DataSet** provides access to values as the correct type at compile time.</span></span> <span data-ttu-id="e5411-111">При использовании строго типизированного **набора данных**ошибки несоответствия типов перехватываются при компиляции кода, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e5411-111">With a strongly typed **DataSet**, type mismatch errors are caught when the code is compiled rather than at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e5411-112">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="e5411-112">In This Section</span></span>  

 [<span data-ttu-id="e5411-113">Создание строго типизированных наборов данных</span><span class="sxs-lookup"><span data-stu-id="e5411-113">Generating Strongly Typed DataSets</span></span>](generating-strongly-typed-datasets.md)  
 <span data-ttu-id="e5411-114">Описывает создание и использование строго типизированного **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="e5411-114">Describes how to create and use a strongly typed **DataSet**.</span></span>  
  
 [<span data-ttu-id="e5411-115">Создание примечаний к типизированным наборам данных</span><span class="sxs-lookup"><span data-stu-id="e5411-115">Annotating Typed DataSets</span></span>](annotating-typed-datasets.md)  
 <span data-ttu-id="e5411-116">Описывает, как закомментировать схему XSD, используемую для создания строго типизированного **набора данных**, чтобы предоставить понятные имена элементам **набора данных** без изменения базовой схемы.</span><span class="sxs-lookup"><span data-stu-id="e5411-116">Describes how to annotate the XML Schema definition language (XSD) schema used to generate a strongly typed **DataSet**, to give **DataSet** elements friendly names without altering the underlying schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5411-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e5411-117">See also</span></span>

- [<span data-ttu-id="e5411-118">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="e5411-118">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="e5411-119">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e5411-119">ADO.NET Overview</span></span>](../ado-net-overview.md)
