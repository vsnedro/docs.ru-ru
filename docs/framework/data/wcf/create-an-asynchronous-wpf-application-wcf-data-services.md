---
description: Дополнительные сведения см. в статье Создание асинхронного приложения Windows Presentation Framework (службы данных WCF).
title: Практическое руководство. Создание асинхронного приложения Windows Presentation Framework (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
ms.openlocfilehash: 8bc8045854ed0b73c06276e2c81e7e03a0ecc8d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766196"
---
# <a name="how-to-create-an-asynchronous-windows-presentation-framework-application-wcf-data-services"></a>Практическое руководство. Создание асинхронного приложения Windows Presentation Framework (службы данных WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

С помощью службы данных WCF можно привязать данные, полученные из службы данных, к элементу пользовательского интерфейса приложения Windows Presentation Framework (WPF). Дополнительные сведения см. [в разделе Привязка данных к элементам управления](binding-data-to-controls-wcf-data-services.md). Вы также можете выполнять операции со службой данных асинхронным способом, что позволяет приложению продолжать отвечать при ожидании ответа на запрос службы данных. Приложения Silverlight обязаны обращаться к службе данных асинхронно. Дополнительные сведения см. в разделе [асинхронные операции](asynchronous-operations-wcf-data-services.md).  
  
 Этот раздел описывает асинхронное обращение к службе данных и привязку результатов к элементам приложения WPF. Примеры в этом разделе используют образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по службы данных WCF](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  

 Ниже приведен код на языке XAML, который определяет окно в приложении WPF.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## <a name="example"></a>Пример  

 Следующая страница с выделенным кодом для файла XAML выполняет асинхронный запрос с использованием службы данных и привязывает результаты к элементам в окне WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## <a name="see-also"></a>См. также

- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
