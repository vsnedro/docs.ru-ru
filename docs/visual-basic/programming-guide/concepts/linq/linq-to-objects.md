---
description: 'Дополнительные сведения: LINQ to Objects (Visual Basic)'
title: LINQ to Objects
ms.date: 07/20/2015
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
ms.openlocfilehash: 50f04c77579595cc78ed43d04e0547eb15f91dc3
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100464772"
---
# <a name="linq-to-objects-visual-basic"></a>LINQ to Objects (Visual Basic)

Термин "LINQ to Objects" означает использование запросов LINQ с любой коллекцией <xref:System.Collections.IEnumerable> или <xref:System.Collections.Generic.IEnumerable%601> напрямую, без привлечения промежуточного поставщика LINQ, API [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) или [LINQ to XML](../../../../standard/linq/linq-xml-overview.md). Вы можете выполнить запрос LINQ к любой перечислимой коллекции, такой как <xref:System.Collections.Generic.List%601>, <xref:System.Array> или <xref:System.Collections.Generic.Dictionary%602>. Коллекция может быть определена пользователем или возвращена API .NET Framework.  
  
 В общем смысле LINQ to Objects представляет собой новый подход к коллекциям. Раньше нужно было написать сложные циклы `For Each`, определяющие порядок извлечения данных из коллекции. При использовании LINQ пишется декларативный код, описывающий, какие данные необходимо извлечь.  
  
 Кроме того, запросы LINQ предлагают три основных преимущества по сравнению с традиционными циклами `For Each`:  
  
1. Они более краткие и удобочитаемые, особенно при фильтрации нескольких условий.  
  
2. Они предоставляют широкие возможности фильтрации, упорядочивания и группировки с минимумом кода приложения.  
  
3. Они могут переноситься в другие источники данных практически без изменений.  
  
 В общем, чем сложнее операция, которую нужно выполнить с данными, тем больше преимуществ вы получаете при использовании LINQ вместо традиционных способов итерации.  
  
 Целью этого раздела является демонстрация подхода LINQ с помощью нескольких примеров. Он не претендует на исчерпывающий характер.  
  
## <a name="in-this-section"></a>В этом разделе  

 [LINQ и строки (Visual Basic)](linq-and-strings.md)  
 Использование LINQ для запроса и преобразования строк и коллекций строк. Ссылки на разделы, демонстрирующие эти принципы.  
  
 [LINQ и отражение (Visual Basic)](linq-and-reflection.md)  
 Ссылки на пример, демонстрирующий, как LINQ использует отражение.  
  
 [LINQ и каталоги файлов (Visual Basic)](linq-and-file-directories.md)  
 Использование LINQ для взаимодействия с файловыми системами. Ссылки на разделы, демонстрирующие эти понятия.  
  
 [Как выполнить запрос к ArrayList с помощью LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md)  
 Выполнение запроса ArrayList в C#.  
  
 [Как добавить пользовательские методы для запросов LINQ (Visual Basic)](how-to-add-custom-methods-for-linq-queries.md)  
 Расширение набора методов, которые можно использовать для запросов LINQ путем добавления методов расширения в интерфейс <xref:System.Collections.Generic.IEnumerable%601>.  
  
 [LINQ (Visual Basic)](index.md)  
 Ссылки на разделы, рассказывающие LINQ и содержащие примеры кода выполнения запросов.
