---
title: Практическое руководство. Выполнение запроса, возвращающего сложные типы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
ms.openlocfilehash: 01958637cedcd6d502d51e9f0821ff3a9faae840
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545328"
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>Практическое руководство. Выполнение запроса, возвращающего сложные типы
В этом разделе показано выполнение запроса на языке [!INCLUDE[esql](../../../../../includes/esql-md.md)], который возвращает объекты типа сущности, содержащие свойство сложного типа.  
  
### <a name="to-run-the-code-in-this-example"></a>Выполнение кода в этом примере  
  
1. Добавьте [модель AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) в проект и настройте проект для использования Entity Framework. Дополнительные сведения см. в разделе [инструкции. Использование мастера EDM](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
2. На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3. Дважды щелкните EDMX файл, чтобы отобразить модель в [окне обозревателя моделей](/previous-versions/dotnet/netframework-4.0/bb738483(v=vs.100)) Entity Designer. На поверхности Entity Designer выберите `Email` `Phone` Свойства и `Contact` типа сущности, щелкните правой кнопкой мыши и выберите **Рефакторинг для нового сложного типа**.  
  
4. В `Email` `Phone` **Обозреватель моделей**добавляется новый сложный тип с выбранными свойствами и. Сложному типу присваивается имя по умолчанию: Переименуйте тип в `EmailPhone` в окне " **свойства** ". Кроме того, новое свойство `ComplexProperty` добавляется к типу сущности `Contact`. Измените имя свойства на `EmailPhoneComplexType.`  
  
     Сведения о создании и изменении сложных типов с помощью мастера EDM см. в разделе [практические руководства. рефакторинг существующих свойств в свойство сложного типа](/previous-versions/dotnet/netframework-4.0/dd456814(v=vs.100)) и [инструкции: создание и изменение сложных типов](/previous-versions/dotnet/netframework-4.0/dd456820(v=vs.100)).  
  
## <a name="example"></a>Пример  
 В следующем примере выполняется запрос, который возвращает коллекцию `Contact` объектов и отображает два свойства `Contact` объектов: `ContactID` и значения `EmailPhoneComplexType` сложного типа.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
