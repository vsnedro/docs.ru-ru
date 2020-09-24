---
title: Определение текста элемента
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: 7389e24f39902edf041c3cd3502303b17fd008ba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164692"
---
# <a name="inferring-element-text"></a>Определение текста элемента

Если элемент содержит текст и не имеет дочерних элементов, которые должны выводиться как таблицы (например, элементы с атрибутами или повторяющиеся элементы), в таблицу, выводимую для элемента, будет добавлен новый столбец с именем **TableName_Text** . Текст, содержащийся в элементе, будет добавлен в строку таблицы и сохранен в новом столбце. Свойству **ColumnMapping** нового столбца будет присвоено значение **MappingType. SimpleContent**.  
  
 Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 В процессе вывода создается таблица с именем **Element1** с двумя столбцами: **attr1** и **Element1_Text**. Свойству **ColumnMapping** столбца **attr1** будет присвоено значение **MappingType. Attribute**. Свойству **ColumnMapping** столбца **Element1_Text** будет присвоено значение **MappingType. SimpleContent**.  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|attr1|Element1_Text|  
|-----------|--------------------|  
|value1|Text1|  
  
 Если элемент содержит текст, а также имеет дочерние элементы, содержащие текст, столбец не будет добавлен в таблицу для хранения текста, содержащегося в элементе. Текст, содержащийся в элементе, пропускается, а текст в дочерних элементах включается в строку таблицы. Например, рассмотрим следующий XML-код:  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 В процессе вывода создается таблица с именем **Element1** с одним столбцом с именем **ChildElement1**. Текст элемента **ChildElement1** будет включаться в строку таблицы. Весь прочий текст будет пропущен. Свойству **ColumnMapping** столбца **ChildElement1** будет присвоено значение **MappingType. element**.  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## <a name="see-also"></a>См. также раздел

- [Определение реляционной структуры набора данных из XML](inferring-dataset-relational-structure-from-xml.md)
- [Загрузка набора данных из XML](loading-a-dataset-from-xml.md)
- [Загрузка сведений о схеме набора данных из XML](loading-dataset-schema-information-from-xml.md)
- [Использование XML в наборах данных](using-xml-in-a-dataset.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
