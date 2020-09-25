---
title: Двоичные данные и данные большого объема SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: a9296e83b0f4e4352423470433670bb2cbe5a248
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183043"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="efb03-102">Двоичные данные и данные большого объема SQL Server</span><span class="sxs-lookup"><span data-stu-id="efb03-102">SQL Server Binary and Large-Value Data</span></span>

<span data-ttu-id="efb03-103">SQL Server предоставляет описатель `max`, который расширяет возможности хранения для типов данных `varchar`, `nvarchar` и `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="efb03-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="efb03-104">Типы данных `varchar(max)`, `nvarchar(max)` и `varbinary(max)` называются *типами данных большого размера*.</span><span class="sxs-lookup"><span data-stu-id="efb03-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="efb03-105">Можно использовать типы данных больших значений для хранения 2^31–1 байт данных.</span><span class="sxs-lookup"><span data-stu-id="efb03-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="efb03-106">В SQL Server 2008 добавлен элемент FILESTREAM. Это не тип данных, а определяемый на уровне столбца атрибут, позволяющий хранить данные большого размера в файловой системе, а не в базе данных.</span><span class="sxs-lookup"><span data-stu-id="efb03-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="efb03-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="efb03-107">In This Section</span></span>  

 [<span data-ttu-id="efb03-108">Изменение данных больших значений (max) в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="efb03-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](modifying-large-value-max-data.md)  
 <span data-ttu-id="efb03-109">Описание работы с типами данных больших значений.</span><span class="sxs-lookup"><span data-stu-id="efb03-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="efb03-110">Данные FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="efb03-110">FILESTREAM Data</span></span>](filestream-data.md)  
 <span data-ttu-id="efb03-111">Описывает, как работать в SQL Server 2008 с данными большого объема, для которых указан атрибут FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="efb03-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb03-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="efb03-112">See also</span></span>

- [<span data-ttu-id="efb03-113">Типы данных SQL Server и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="efb03-113">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="efb03-114">SQL Serverные операции с данными в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="efb03-114">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="efb03-115">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="efb03-115">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="efb03-116">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="efb03-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
