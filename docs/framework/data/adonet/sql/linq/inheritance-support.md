---
title: Поддержка наследования
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 7673e69458d5c1af854747c43ba463332a9cd588
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158257"
---
# <a name="inheritance-support"></a><span data-ttu-id="7b4b4-102">Поддержка наследования</span><span class="sxs-lookup"><span data-stu-id="7b4b4-102">Inheritance Support</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7b4b4-103">поддерживает *однотабличное сопоставление*.</span><span class="sxs-lookup"><span data-stu-id="7b4b4-103">supports *single-table mapping*.</span></span> <span data-ttu-id="7b4b4-104">Другими словами, в одной таблице базы данных хранится полная иерархия наследования.</span><span class="sxs-lookup"><span data-stu-id="7b4b4-104">In other words, a complete inheritance hierarchy is stored in a single database table.</span></span> <span data-ttu-id="7b4b4-105">Таблица содержит плоское объединение всех возможных столбцов данных для всей иерархии.</span><span class="sxs-lookup"><span data-stu-id="7b4b4-105">The table contains the flattened union of all possible data columns for the whole hierarchy.</span></span> <span data-ttu-id="7b4b4-106">(Объединение — это результат объединения двух таблиц в одну таблицу, которая содержит строки, которые присутствовали в одной из исходных таблиц.) Каждая строка имеет значения NULL в столбцах, которые не применяются к типу экземпляра, представленного строкой.</span><span class="sxs-lookup"><span data-stu-id="7b4b4-106">(A union is the result of combining two tables into one table that has the rows that were present in either of the original tables.) Each row has nulls in the columns that do not apply to the type of the instance represented by the row.</span></span>  
  
 <span data-ttu-id="7b4b4-107">Стратегия однотабличного сопоставления представляет собой простейшее представление наследования и обеспечивает высокую производительность для многих различных категорий запросов.</span><span class="sxs-lookup"><span data-stu-id="7b4b4-107">The single-table mapping strategy is the simplest representation of inheritance and provides good performance characteristics for many different categories of queries.</span></span>  
  
 <span data-ttu-id="7b4b4-108">Чтобы реализовать данное сопоставление в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], в корневом классе иерархии наследования необходимо указать атрибуты и свойства атрибутов.</span><span class="sxs-lookup"><span data-stu-id="7b4b4-108">To implement this mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you must specify the attributes and attribute properties on the root class of the inheritance hierarchy.</span></span> <span data-ttu-id="7b4b4-109">Дополнительные сведения см. [в разделе Инструкции: Map иерархии наследования](how-to-map-inheritance-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="7b4b4-109">For more information, see [How to: Map Inheritance Hierarchies](how-to-map-inheritance-hierarchies.md).</span></span>  
  
 <span data-ttu-id="7b4b4-110">Разработчики, использующие Visual Studio, также могут использовать реляционный конструктор объектов для отображения иерархий наследования.</span><span class="sxs-lookup"><span data-stu-id="7b4b4-110">Developers using Visual Studio can also use the Object Relational Designer to map inheritance hierarchies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b4b4-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7b4b4-111">See also</span></span>

- [<span data-ttu-id="7b4b4-112">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="7b4b4-112">Background Information</span></span>](background-information.md)
