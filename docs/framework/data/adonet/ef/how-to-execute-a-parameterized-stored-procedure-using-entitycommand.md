---
title: Практическое руководство. Выполнение параметризованной хранимой процедуры с использованием EntityCommand
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
ms.openlocfilehash: 7a055fc3e62821285fe2b6e1333d516c477d025b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549761"
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a><span data-ttu-id="91e21-102">Практическое руководство. Выполнение параметризованной хранимой процедуры с использованием EntityCommand</span><span class="sxs-lookup"><span data-stu-id="91e21-102">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>
<span data-ttu-id="91e21-103">В данном разделе приведен пример выполнения параметризированной хранимой процедуры при помощи команды <xref:System.Data.EntityClient.EntityCommand>.</span><span class="sxs-lookup"><span data-stu-id="91e21-103">This topic shows how to execute a parameterized stored procedure by using the <xref:System.Data.EntityClient.EntityCommand> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="91e21-104">Выполнение кода в этом примере</span><span class="sxs-lookup"><span data-stu-id="91e21-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="91e21-105">Добавьте [модель School](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) в проект и настройте проект для использования Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="91e21-105">Add the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="91e21-106">Дополнительные сведения см. в разделе [инструкции. Использование мастера EDM](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="91e21-106">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="91e21-107">На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="91e21-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. <span data-ttu-id="91e21-108">Импортируйте хранимую процедуру `GetStudentGrades` и укажите сущности `CourseGrade` в качестве типа возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="91e21-108">Import the `GetStudentGrades` stored procedure and specify `CourseGrade` entities as a return type.</span></span> <span data-ttu-id="91e21-109">Сведения о том, как импортировать хранимую процедуру, см. в разделе [инструкции. Импорт хранимой процедуры](/previous-versions/dotnet/netframework-4.0/bb896231(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="91e21-109">For information on how to import a stored procedure, see [How to: Import a Stored Procedure](/previous-versions/dotnet/netframework-4.0/bb896231(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91e21-110">Пример</span><span class="sxs-lookup"><span data-stu-id="91e21-110">Example</span></span>  
 <span data-ttu-id="91e21-111">Следующий код выполняет хранимую процедуру `GetStudentGrades`, где параметр `StudentId` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="91e21-111">The following code executes the `GetStudentGrades` stored procedure where `StudentId` is a required parameter.</span></span> <span data-ttu-id="91e21-112">Затем результаты считываются объектом <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="91e21-112">The results are then read by an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="91e21-113">См. также</span><span class="sxs-lookup"><span data-stu-id="91e21-113">See also</span></span>

- [<span data-ttu-id="91e21-114">Поставщик EntityClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="91e21-114">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
