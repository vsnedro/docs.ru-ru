---
description: 'Дополнительные сведения см. в статье как создать объектную модель в Visual Basic или C. #'
title: Практическое руководство. Как создать модель объектов на языке Visual Basic или C#
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: d842a646f9f6186d252d10297618ddc2cb137e70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785969"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a>Как создать объектную модель в Visual Basic или C\#

В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объектная модель используемого языка программирования сопоставляется с реляционной базой данных. Доступны два средства для автоматического создания Visual Basic или модели C# на основе метаданных существующей базы данных.  
  
- При использовании Visual Studio можно использовать реляционный конструктор объектов для создания объектной модели. Реляционный конструктор объектов (R) предоставляет богатый пользовательский интерфейс, помогающий в создании [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объектной модели. Дополнительные сведения см. [в разделе средства LINQ to SQL в Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).
  
- Средство командной строки SQLMetal. Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
    > [!NOTE]
    > Если существующие базы данных отсутствуют и необходимо создать базу данных из объектной модели, можно создать объектную модель с помощью редактора кода и метода <xref:System.Data.Linq.DataContext.CreateDatabase%2A>. Дополнительные сведения см. [в разделе инструкции. динамическое создание базы данных](how-to-dynamically-create-a-database.md).  
  
 Документация для реляционного конструктора объектов (R) содержит примеры создания объектной модели Visual Basic или C# с помощью конструктора O/R. Ниже приведены примеры использования программы командной строки SQLMetal. Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Пример  

 Командная строка SQLMetal, показанная в следующем примере, создает Visual Basic код в качестве объектной модели на основе атрибутов образца базы данных Northwind. Также отображаются хранимые процедуры и функции.  
  
```console  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a>Пример  

 С помощью команды программы SQLMetal, представленной в следующем примере, создается код C# для основанной на атрибутах объектной модели базы данных "Northwind". Также отображаются хранимые процедуры и функции и имена таблиц автоматически преобразуются в имена во множественном числе.  
  
```console  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию](programming-guide.md)
- [Модель объектов LINQ to SQL](the-linq-to-sql-object-model.md)
- [Обучение с использованием пошаговых руководств](learning-by-walkthroughs.md)
- [Практическое руководство. Как настроить классы сущностей с помощью редактора кода](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Сопоставление, основанное на атрибутах](attribute-based-mapping.md)
- [SqlMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [Внешнее сопоставление](external-mapping.md)
- [Загрузка примеров баз данных](downloading-sample-databases.md)
- [Создание модели объектов](creating-the-object-model.md)
