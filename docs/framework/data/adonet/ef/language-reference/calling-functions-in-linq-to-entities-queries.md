---
title: Вызов функций в запросах LINQ to Entities
description: Используйте эти статьи, чтобы увидеть, как классы Ентитифунктионс и Склфунктионс предоставляют доступ к каноническим и функциям базы данных в составе Entity Framework.
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: faa6406713592f10e5e7371cd73f29bec4b03b7b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286861"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a>Вызов функций в запросах LINQ to Entities
В подразделах этого раздела описывается вызов функций в запросах LINQ to Entities.  
  
 Классы <xref:System.Data.Objects.EntityFunctions> и <xref:System.Data.Objects.SqlClient.SqlFunctions> обеспечивают доступ к каноническим функциям и функциям базы данных посредством платформы Entity Framework. Дополнительные сведения см. в статьях [как вызывать канонические функции](how-to-call-canonical-functions.md) и [как вызывать функции базы данных](how-to-call-database-functions.md).  
  
 Процесс вызова пользовательской функции состоит из трех основных шагов.  
  
1. Определите функцию в концептуальной модели или объявите функцию в модели хранения.  
  
2. Добавьте метод в приложение и сопоставьте его с функцией в модели с помощью <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.  
  
3. Вызовите функцию в запросе LINQ to Entities.  
  
 Дополнительные сведения см. в подразделах этого раздела.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Вызов канонических функций](how-to-call-canonical-functions.md)  
  
 [Практическое руководство. Вызов функций базы данных](how-to-call-database-functions.md)  
  
 [Практическое руководство. Вызов настраиваемых функций базы данных](how-to-call-custom-database-functions.md)  
  
 [Практическое руководство. Вызов определенных моделью функций в запросах](how-to-call-model-defined-functions-in-queries.md)  
  
 [Практическое руководство. Вызов определенных моделью функций как методов объектов](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a>См. также

- [Запросы в LINQ to Entities](queries-in-linq-to-entities.md)
- [Канонические функции](canonical-functions.md)
- [Общие сведения о EDMX-файлах](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Как определять настраиваемые функции в концептуальной модели](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))
