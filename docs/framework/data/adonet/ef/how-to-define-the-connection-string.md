---
description: Дополнительные сведения см. в статье как определить строку подключения.
title: Практическое руководство. Определение строки соединения
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 104264299e597bc142a689aa83f3207765d18c67
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650824"
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
