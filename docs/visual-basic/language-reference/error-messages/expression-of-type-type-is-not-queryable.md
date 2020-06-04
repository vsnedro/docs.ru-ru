---
title: Выражение типа <type> не доступно для запроса
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: e61b4dac109f714b5cf25226d1029237ca77032d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409482"
---
# <a name="expression-of-type-type-is-not-queryable"></a><span data-ttu-id="f60d2-102">Выражение типа \<type> не доступно для запроса</span><span class="sxs-lookup"><span data-stu-id="f60d2-102">Expression of type \<type> is not queryable</span></span>
<span data-ttu-id="f60d2-103">Выражение типа \<type> не может быть доступно для запросов.</span><span class="sxs-lookup"><span data-stu-id="f60d2-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="f60d2-104">Убедитесь, что отсутствует ссылка на сборку и (или) импорт пространства имен для поставщика LINQ.</span><span class="sxs-lookup"><span data-stu-id="f60d2-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="f60d2-105">Запрашиваемые типы определяются в <xref:System.Linq> <xref:System.Data.Linq> <xref:System.Xml.Linq> пространствах имен, и.</span><span class="sxs-lookup"><span data-stu-id="f60d2-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="f60d2-106">Для выполнения запросов LINQ необходимо импортировать одно или несколько из этих пространств имен.</span><span class="sxs-lookup"><span data-stu-id="f60d2-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="f60d2-107"><xref:System.Linq>Пространство имен позволяет запрашивать объекты, такие как коллекции и массивы, с помощью LINQ.</span><span class="sxs-lookup"><span data-stu-id="f60d2-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="f60d2-108">Это <xref:System.Data.Linq> пространство имен позволяет запрашивать наборы данных ADO.NET и SQL Server с помощью LINQ.</span><span class="sxs-lookup"><span data-stu-id="f60d2-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="f60d2-109"><xref:System.Xml.Linq>Пространство имен позволяет запрашивать XML-код с помощью LINQ и использовать функции XML в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f60d2-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="f60d2-110">**Идентификатор ошибки:** BC36593</span><span class="sxs-lookup"><span data-stu-id="f60d2-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f60d2-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f60d2-111">To correct this error</span></span>  
  
1. <span data-ttu-id="f60d2-112">Добавьте `Import` оператор для <xref:System.Linq> <xref:System.Data.Linq> <xref:System.Xml.Linq> пространства имен, или в файл кода.</span><span class="sxs-lookup"><span data-stu-id="f60d2-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="f60d2-113">Также можно импортировать пространства имен для проекта с помощью страницы **ссылки** в конструкторе проектов (**Мой проект**).</span><span class="sxs-lookup"><span data-stu-id="f60d2-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2. <span data-ttu-id="f60d2-114">Убедитесь, что тип, определенный в качестве источника запроса, является запрашиваемым типом.</span><span class="sxs-lookup"><span data-stu-id="f60d2-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="f60d2-115">То есть тип, реализующий <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601> .</span><span class="sxs-lookup"><span data-stu-id="f60d2-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60d2-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f60d2-116">See also</span></span>

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- <span data-ttu-id="f60d2-117">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f60d2-117">[Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="f60d2-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="f60d2-118">LINQ</span></span>](../../programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="f60d2-119">XML</span><span class="sxs-lookup"><span data-stu-id="f60d2-119">XML</span></span>](../../programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="f60d2-120">Ссылки и оператор Imports</span><span class="sxs-lookup"><span data-stu-id="f60d2-120">References and the Imports Statement</span></span>](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="f60d2-121">Оператор Imports (пространство имен .NET и тип)</span><span class="sxs-lookup"><span data-stu-id="f60d2-121">Imports Statement (.NET Namespace and Type)</span></span>](../statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="f60d2-122">Страница "Ссылки" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f60d2-122">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
