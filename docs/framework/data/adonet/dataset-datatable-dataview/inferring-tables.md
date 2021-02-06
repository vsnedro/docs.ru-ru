---
description: Дополнительные сведения о Выведение таблиц
title: Определение таблиц
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 00a24cbfc44aea4279b0a115214ec26d3eac59ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652163"
---
# <a name="inferring-tables"></a>Определение таблиц

При выведении схемы для <xref:System.Data.DataSet> из XML-документа ADO.NET сначала определяет, какой из XML-элементов представляет таблицы. Следующие XML-структуры приводят к созданию таблицы для схемы **набора данных** :  
  
- Элементы с атрибутами.  
  
- Элементы с дочерними элементами.  
  
- Повторяющиеся элементы.  
  
## <a name="elements-with-attributes"></a>Элементы с атрибутами  

 Элементы с заданными атрибутами приводятся в выведенных таблицах. Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 В процессе вывода создается таблица с именем Element1.  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|attr1|Element1_Text|  
|-----------|--------------------|  
|value1||  
|value2|Text1|  
  
## <a name="elements-with-child-elements"></a>Элементы с дочерними элементами  

 Элементы, имеющие дочерние элементы, приводятся в выведенных таблицах. Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 В процессе вывода создается таблица с именем Element1.  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text1|  
  
 Элемент документа или корневой элемент приводится в выведенной таблице, если он имеет атрибуты или дочерние элементы, которые выводятся в виде столбцов. Если элемент документа не имеет атрибутов и не содержит дочерних элементов, которые будут выводиться как столбцы, то элемент выводится как **набор данных**. Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 В процессе вывода создается таблица с именем DocumentElement.  
  
 **Набор данных:** невдатасет  
  
 **Таблица:** DocumentElement  
  
|Element1|Element2|  
|--------------|--------------|  
|Text1|Text2|  
  
 В качестве альтернативы рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 Процесс вывода создает **набор данных** с именем «documentElement», содержащий таблицу с именем «Element1».  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="repeating-elements"></a>Повторяющиеся элементы  

 Повторяющиеся элементы приводятся в выведенной таблице. Например, рассмотрим следующий XML-код:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 В процессе вывода создается таблица с именем Element1.  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
## <a name="see-also"></a>См. также

- [Определение реляционной структуры набора данных из XML](inferring-dataset-relational-structure-from-xml.md)
- [Загрузка набора данных из XML](loading-a-dataset-from-xml.md)
- [Загрузка сведений о схеме набора данных из XML](loading-dataset-schema-information-from-xml.md)
- [Использование XML в наборах данных](using-xml-in-a-dataset.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
