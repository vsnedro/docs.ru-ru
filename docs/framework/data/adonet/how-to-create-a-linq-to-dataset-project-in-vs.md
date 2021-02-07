---
description: Дополнительные сведения см. в статье Создание проекта LINQ to DataSet в Visual Studio.
title: Создание проекта LINQ to DataSet в Visual Studio
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 4ab626ddaa27780759df95462faac366be8beeff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723833"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>Руководство. Создание проекта LINQ to DataSet в Visual Studio

Для различных типов проектов LINQ требуются определенные ссылки на сборки и импортированные пространства имен (Visual Basic) или директивы [using](../../../csharp/language-reference/keywords/using-directive.md) (C#). Минимальное требование LINQ — это ссылка на *System.Core.dll* и `using` директиву для <xref:System.Linq> .

Эти требования предоставляются по умолчанию при создании нового проекта консольного приложения C# в Visual Studio 2017 или более поздней версии. Если вы обновляете проект с более ранней версии Visual Studio, вам может потребоваться предоставить эти ссылки, связанные с LINQ, вручную.

Для LINQ to DataSet требуются две дополнительные ссылки на *System.Data.dll* и *System.Data.DataSetExtensions.dll*.

> [!NOTE]
> При построении из командной строки необходимо вручную ссылаться на библиотеки DLL, связанные с LINQ, в *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*.

## <a name="to-enable-linq-to-dataset-functionality"></a>Включение функциональности LINQ to DataSet

Выполните следующие действия, чтобы включить LINQ to DataSet функциональности в существующем проекте.

1. Добавьте ссылки на **System. Core**, **System. Data** и **System. Data. DataSetExtensions**.

   В **Обозреватель решений** щелкните правой кнопкой мыши узел **ссылки** и выберите команду **Добавить ссылку**. В диалоговом окне **Диспетчер ссылок** выберите **System. Core**, **System. Data** и **System. Data. DataSetExtensions**. Выберите **ОК**.

1. Добавьте директивы [using](../../../csharp/language-reference/keywords/using-directive.md) (или [импортирует операторы](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) в Visual Basic) для **System. Data** и **System. LINQ**.

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. При необходимости добавьте `using` директиву (или `Imports` оператор) для **System. Data. Common** или **System. Data. SqlClient** в зависимости от способа подключения к базе данных.

## <a name="see-also"></a>См. также

- [Начало работы с LINQ to DataSet](getting-started-linq-to-dataset.md)
