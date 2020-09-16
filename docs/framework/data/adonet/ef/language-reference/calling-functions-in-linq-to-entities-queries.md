---
title: Вызов функций в запросах LINQ to Entities
description: Используйте эти статьи, чтобы увидеть, как классы Ентитифунктионс и Склфунктионс предоставляют доступ к каноническим и функциям базы данных в составе Entity Framework.
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: eb206e9b331da1ae442c1f310e78fec5c6b57e82
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546052"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a>Вызов функций в запросах LINQ to Entities
В подразделах этого раздела описывается вызов функций в запросах LINQ to Entities.  
  
 Классы <xref:System.Data.Objects.EntityFunctions> и <xref:System.Data.Objects.SqlClient.SqlFunctions> обеспечивают доступ к каноническим функциям и функциям базы данных посредством платформы Entity Framework. Дополнительные сведения см. в статьях [как вызывать канонические функции](how-to-call-canonical-functions.md) и [как вызывать функции базы данных](how-to-call-database-functions.md).  
  
 Процесс вызова пользовательской функции состоит из трех основных шагов.  
  
1. Определите функцию в концептуальной модели или объявите функцию в модели хранения.  
  
2. Добавьте метод в приложение и сопоставьте его с функцией в модели с помощью <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.  
  
3. Вызовите функцию в запросе LINQ to Entities.  
  
 Дополнительные сведения см. в подразделах этого раздела.  
  
## <a name="in-this-section"></a>в этом разделе  
 [Практическое руководство. Вызов канонических функций](how-to-call-canonical-functions.md)  
  
 [Практическое руководство. Вызов функций базы данных](how-to-call-database-functions.md)  
  
 [Практическое руководство. Вызов настраиваемых функций базы данных](how-to-call-custom-database-functions.md)  
  
 [Практическое руководство. Вызов определенных моделью функций в запросах](how-to-call-model-defined-functions-in-queries.md)  
  
 [Практическое руководство. Вызов определенных моделью функций как методов объектов](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a>См. также

- [Запросы в LINQ to Entities](queries-in-linq-to-entities.md)
- [Канонические функции](canonical-functions.md)
- [Общие сведения о EDMX-файлах](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Как определять настраиваемые функции в концептуальной модели](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))
