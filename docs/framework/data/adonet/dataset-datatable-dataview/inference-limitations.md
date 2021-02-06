---
description: 'Дополнительные сведения: ограничения на вывод'
title: Ограничения определения
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 926e456acfc5eac2598be40490b72523facfd058
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652267"
---
# <a name="inference-limitations"></a>Ограничения определения

Процесс вывода схемы <xref:System.Data.DataSet> из XML-кода может приводиться в различных схемах в зависимости от XML-элементов в каждом документе. Например, рассмотрим следующие XML-документы.  
  
 Document1:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 Document2:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 Для "document1" процесс вывода создает **набор данных** с именем "documentElement" и таблицу с именем "Element1", так как "Element1" является повторяющимся элементом.  
  
 **Набор данных:** DocumentElement  
  
 **Таблица:** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
 Однако для "Document2" процесс вывода создает **набор данных** с именем "невдатасет" и таблицу с именем "documentElement". Element1 выводится в виде столбца, потому что не имеет атрибутов и дочерних элементов.  
  
 **Набор данных:** невдатасет  
  
 **Таблица:** DocumentElement  
  
|Element1|  
|--------------|  
|Text1|  
  
 Эти два XML-документа, возможно, должны были выдавать одну и ту же схему, но процесс вывода дает значительно различающиеся результаты в зависимости от элементов, содержащихся в каждом документе.  
  
 Чтобы избежать расхождений, которые могут возникнуть при формировании схемы из XML-документа, рекомендуется явно указать схему с помощью языка определения схемы XML (XSD) или XML-Data Reduced (XDR) при загрузке **набора данных** из XML. Дополнительные сведения о явном указании схемы **набора данных** с XML-схемой см. [в разделе Наследование реляционной структуры набора данных из схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
## <a name="see-also"></a>См. также

- [Определение реляционной структуры набора данных из XML](inferring-dataset-relational-structure-from-xml.md)
- [Загрузка набора данных из XML](loading-a-dataset-from-xml.md)
- [Загрузка сведений о схеме набора данных из XML](loading-dataset-schema-information-from-xml.md)
- [Использование XML в наборах данных](using-xml-in-a-dataset.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
