---
title: Практическое руководство. Определение строки соединения
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 9b029644e0d4e4c7467fbe1e1144579e6edb3478
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536214"
---
# <a name="how-to-define-the-connection-string"></a>Практическое руководство. Определение строки соединения

В этом разделе показано, как определить строку соединения, используемую при подключении к концептуальной модели. Этот раздел основан на концептуальной модели [AdventureWorks Sales](/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) . Модель AdventureWorks Sales используется во всех разделах документации платформы Entity Framework, описывающих выполнение задач. В этом разделе предполагается, что вы уже настроили Entity Framework и определили модель AdventureWorks Sales. Дополнительные сведения см. в разделе [руководство. Определение файлов модели и сопоставления вручную](/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)). Процедуры, описанные в этом разделе, также включены в [руководство по ручной настройке проекта Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).

> [!NOTE]
> При использовании мастера EDM в проекте Visual Studio он автоматически создает EDMX-файл и настраивает проект для использования Entity Framework. Дополнительные сведения см. в разделе [инструкции. Использование мастера EDM](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).

## <a name="to-define-the-entity-framework-connection-string"></a>Определение строки соединения Entity Framework

- Откройте файл конфигурации приложения (app.config) и добавьте следующую строку соединения:

```xml
<connectionStrings>
    <add name="AdventureWorksEntities"
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

Если в проекте нет файла конфигурации приложения, его можно добавить, выбрав в меню **проект** пункт **Добавить новый элемент** , выбрав категорию **Общие** , выбрав **файл конфигурации приложения**, а затем нажав кнопку **Добавить**.

## <a name="see-also"></a>См. также

- [Краткое руководство](/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [Как создать новый EDMX-файл](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [Средства работы с моделью EDM ADO.NET](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
