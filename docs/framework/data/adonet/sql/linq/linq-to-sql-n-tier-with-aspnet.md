---
description: 'Дополнительные сведения: LINQ to SQL N-Tiered with ASP.NET'
title: N-уровневое использование LINQ to SQL с ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: a455525f8f0bbef38487b058d89fd2c9b4dda377
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803806"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>N-уровневое использование LINQ to SQL с ASP.NET

В приложениях ASP.NET, использующих [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , используется <xref:System.Web.UI.WebControls.LinqDataSource> Серверный веб-элемент управления. Элемент управления обрабатывает большую часть логики, которую необходимо выполнить для запроса [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , передачи данных в браузер, их извлечения и отправки в, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> который затем обновляет базу данных. Чтобы элемент управления полностью обрабатывал передачу данных между [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и браузером, достаточно настроить его в разметке. Поскольку элемент управления обрабатывает взаимодействие с уровнем представления и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] обрабатывает связь с уровнем данных, основное внимание в ASP.NET многоуровневых приложениях заключается в написании пользовательской бизнес-логики.  
  
 Дополнительные сведения о `LINQDataSource` см. в разделе [Общие сведения о серверном веб-элементе управления LinqDataSource](/previous-versions/aspnet/bb547113(v=vs.100)).  
  
## <a name="see-also"></a>См. также

- [N-уровневые и удаленные приложения с LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md)
