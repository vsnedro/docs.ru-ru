---
title: Навигация по таблицам данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 9b7ed4ef1dbe141d8f6a1b6c6b9af2fd89e6c7af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148312"
---
# <a name="navigating-datatables"></a><span data-ttu-id="1913c-102">Навигация по таблицам данных</span><span class="sxs-lookup"><span data-stu-id="1913c-102">Navigating DataTables</span></span>

<span data-ttu-id="1913c-103">Объект <xref:System.Data.DataTableReader> получает содержимое одного или нескольких объектов <xref:System.Data.DataTable> в виде одного или нескольких однопроходных результирующих наборов, доступных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1913c-103">The <xref:System.Data.DataTableReader> obtains the contents of one or more <xref:System.Data.DataTable> objects in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="1913c-104">Объект <xref:System.Data.DataTableReader> может содержать несколько результирующих наборов, если он создан методом <xref:System.Data.DataSet.CreateDataReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="1913c-104">A <xref:System.Data.DataTableReader> may contain multiple result sets if it is created by using the <xref:System.Data.DataSet.CreateDataReader%2A> method.</span></span> <span data-ttu-id="1913c-105">Если имеется несколько результирующих наборов, метод <xref:System.Data.DataTableReader.NextResult%2A> продвигает курсор к следующему результирующему набору.</span><span class="sxs-lookup"><span data-stu-id="1913c-105">When there is more than one result set, the <xref:System.Data.DataTableReader.NextResult%2A> method advances the cursor to the next result set.</span></span> <span data-ttu-id="1913c-106">Это однопроходной процесс.</span><span class="sxs-lookup"><span data-stu-id="1913c-106">This is a forward-only process.</span></span> <span data-ttu-id="1913c-107">Вернуться к предыдущему результирующему набору невозможно.</span><span class="sxs-lookup"><span data-stu-id="1913c-107">It is not possible to return to a previous result set.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1913c-108">Пример</span><span class="sxs-lookup"><span data-stu-id="1913c-108">Example</span></span>  

 <span data-ttu-id="1913c-109">В следующем примере `TestConstructor` метод создает два <xref:System.Data.DataTable> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1913c-109">In the following example, the `TestConstructor` method creates two <xref:System.Data.DataTable> instances.</span></span> <span data-ttu-id="1913c-110">Чтобы продемонстрировать этот конструктор для <xref:System.Data.DataTableReader> класса, в примере создается новый **DataTableReader** на основе массива, содержащего два **объекта DataTables**, и выполняется простая операция печати содержимого из первых нескольких столбцов в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="1913c-110">In order to demonstrate this constructor for the <xref:System.Data.DataTableReader> class, the sample creates a new **DataTableReader** based on an array that contains the two **DataTables**, and performs a simple operation, printing the contents from the first few columns to the console window.</span></span>  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1913c-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1913c-111">See also</span></span>

- [<span data-ttu-id="1913c-112">Объекты DataTableReader</span><span class="sxs-lookup"><span data-stu-id="1913c-112">DataTableReaders</span></span>](datatablereaders.md)
- [<span data-ttu-id="1913c-113">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1913c-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
