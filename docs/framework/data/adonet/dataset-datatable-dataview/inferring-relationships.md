---
description: Дополнительные сведения о выведение связей
title: Определение отношений
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: a117581d512c1427c638ea862169ab3c7623d783
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652150"
---
# <a name="inferring-relationships"></a>Определение отношений

Если элемент, выводимый в виде таблицы, имеет дочерний элемент, который также выводится в виде таблицы, между двумя этими таблицами будет создана связь <xref:System.Data.DataRelation>. Новый столбец с именем **ParentTableName_Id** будет добавлен как в таблицу, созданную для родительского элемента, так и на таблицу, созданную для дочернего элемента. Свойству **ColumnMapping** этого столбца идентификаторов будет присвоено значение **MappingType. Hidden**. Столбец будет автоматически инкрементным первичным ключом для родительской таблицы и будет использоваться для **связи DataRelation** между двумя таблицами. Тип данных добавленного столбца идентификаторов будет **System. Int32**, в отличие от типа данных всех других выводимых столбцов, которые имеют тип **System. String**. Объект <xref:System.Data.ForeignKeyConstraint> с **DeleteRule**  =  **CASCADE** также будет создан с помощью нового столбца как в родительской, так и в дочерней таблице.  
  
 Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Процесс вывода приведет к созданию двух таблиц: **Element1** и **ChildElement1**.  
  
 Таблица **Element1** будет содержать два столбца: **Element1_Id** и **ChildElement2**. Свойству **ColumnMapping** столбца **Element1_Id** будет присвоено значение **MappingType. Hidden**. Свойству **ColumnMapping** столбца **ChildElement2** будет присвоено значение **MappingType. element**. Столбец **Element1_Id** будет установлен в качестве первичного ключа таблицы **Element1** .  
  
 Таблица **ChildElement1** будет содержать три столбца: **attr1**, **attr2** и **Element1_Id**. Свойству **ColumnMapping** для столбцов **attr1** и **attr2** будет присвоено значение **MappingType. Attribute**. Свойству **ColumnMapping** столбца **Element1_Id** будет присвоено значение **MappingType. Hidden**.  
  
 **DataRelation** и **ForeignKeyConstraint** будут созданы с использованием **Element1_Id** столбцов из обеих таблиц.  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Таблица:** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation:** Element1_ChildElement1  
  
 **Паренттабле:** Element1  
  
 **Парентколумн:** Element1_Id  
  
 **ChildTable:** ChildElement1  
  
 **Чилдколумн:** Element1_Id  
  
 **Вложенные:** Условия  
  
 **ForeignKeyConstraint:** Element1_ChildElement1  
  
 **Столбец:** Element1_Id  
  
 **Паренттабле:** Element1  
  
 **ChildTable:** ChildElement1  
  
 **DeleteRule:** Аргумент  
  
 **Акцептрежектруле:** None  
  
## <a name="see-also"></a>См. также

- [Определение реляционной структуры набора данных из XML](inferring-dataset-relational-structure-from-xml.md)
- [Загрузка набора данных из XML](loading-a-dataset-from-xml.md)
- [Загрузка сведений о схеме набора данных из XML](loading-dataset-schema-information-from-xml.md)
- [Вложение отношений DataRelation](nesting-datarelations.md)
- [Использование XML в наборах данных](using-xml-in-a-dataset.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
