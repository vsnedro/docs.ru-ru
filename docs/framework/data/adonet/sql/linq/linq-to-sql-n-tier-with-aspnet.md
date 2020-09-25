---
title: N-уровневое использование LINQ to SQL с ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: a184c9dcb29e7994aefa4062be2b30484539c4e1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175321"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a><span data-ttu-id="e0883-102">N-уровневое использование LINQ to SQL с ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e0883-102">LINQ to SQL N-Tier with ASP.NET</span></span>

<span data-ttu-id="e0883-103">В приложениях ASP.NET, использующих [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , используется <xref:System.Web.UI.WebControls.LinqDataSource> Серверный веб-элемент управления.</span><span class="sxs-lookup"><span data-stu-id="e0883-103">In ASP.NET applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you use the <xref:System.Web.UI.WebControls.LinqDataSource> Web server control.</span></span> <span data-ttu-id="e0883-104">Элемент управления обрабатывает большую часть логики, которую необходимо выполнить для запроса [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , передачи данных в браузер, их извлечения и отправки в, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> который затем обновляет базу данных.</span><span class="sxs-lookup"><span data-stu-id="e0883-104">The control handles most of the logic that it must have to query against [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], pass the data to the browser, retrieve it, and submit it to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> which then updates the database.</span></span> <span data-ttu-id="e0883-105">Чтобы элемент управления полностью обрабатывал передачу данных между [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и браузером, достаточно настроить его в разметке.</span><span class="sxs-lookup"><span data-stu-id="e0883-105">You just configure the control in the markup, and the control handles all the data transfer between [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] and the browser.</span></span> <span data-ttu-id="e0883-106">Поскольку элемент управления обрабатывает взаимодействие с уровнем представления и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] обрабатывает связь с уровнем данных, основное внимание в ASP.NET многоуровневых приложениях заключается в написании пользовательской бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="e0883-106">Because the control handles the interactions with the presentation tier, and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] handles the communication with the data tier, your main focus in ASP.NET multitier applications is on writing your custom business logic.</span></span>  
  
 <span data-ttu-id="e0883-107">Дополнительные сведения о `LINQDataSource` см. в разделе [Общие сведения о серверном веб-элементе управления LinqDataSource](/previous-versions/aspnet/bb547113(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e0883-107">For more information about `LINQDataSource`, see [LinqDataSource Web Server Control Overview](/previous-versions/aspnet/bb547113(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0883-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e0883-108">See also</span></span>

- [<span data-ttu-id="e0883-109">N-уровневые и удаленные приложения с LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e0883-109">N-Tier and Remote Applications with LINQ to SQL</span></span>](n-tier-and-remote-applications-with-linq-to-sql.md)
