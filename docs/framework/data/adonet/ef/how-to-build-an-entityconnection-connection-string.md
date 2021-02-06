---
description: Дополнительные сведения см. в статье как создать строку подключения EntityConnection.
title: Практическое руководство. Сборка строки соединения EntityConnection
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5bd1a748-3df7-4d0a-a607-14f25e3175e9
ms.openlocfilehash: 760ed9d1f362e08135586a56a6b900afcd2b13bd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650837"
---
# <a name="how-to-build-an-entityconnection-connection-string"></a>Практическое руководство. Сборка строки соединения EntityConnection

В этом разделе содержится пример создания экземпляра <xref:System.Data.EntityClient.EntityConnection>.  
  
### <a name="to-run-the-code-in-this-example"></a>Выполнение кода в этом примере  
  
1. Добавьте [модель AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) в проект и настройте проект для использования Entity Framework. Дополнительные сведения см. в разделе [инструкции. Использование мастера EDM](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
2. На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Пример  

 В следующем примере инициализируется объект <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> для базового поставщика, инициализируется объект <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType>, а затем этот объект передается конструктору <xref:System.Data.EntityClient.EntityConnection>.  
  
 [!code-csharp[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#buildingconnectionstringwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#buildingconnectionstringwithentitycommand)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Использование EntityConnection с контекстом объекта](/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))
- [Поставщик EntityClient для Entity Framework](entityclient-provider-for-the-entity-framework.md)
