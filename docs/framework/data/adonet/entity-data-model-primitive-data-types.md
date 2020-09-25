---
title: 'EDM (модель данных с использованием сущностей): примитивные типы данных'
ms.date: 03/30/2017
ms.assetid: 7635168e-0566-4fdd-8391-7941b0d9f787
ms.openlocfilehash: 4d52f50dec44c7d667dfedc10a2c9c25fcde8917
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194821"
---
# <a name="entity-data-model-primitive-data-types"></a>EDM (модель данных с использованием сущностей): примитивные типы данных

EDM (EDM) поддерживает набор абстрактных примитивных типов данных (например, String, Boolean, Int32 и т. д.), которые используются для определения [свойств](property.md) в концептуальной модели. Эти примитивные типы данных являются посредниками для фактических примитивных типов данных, которые поддерживаются в среде хранения или размещения, такой как база данных сервера SQL или среда CLR. Модель EDM не определяет семантику операций или преобразований для примитивных типов данных; такая семантика определяется средой хранения или размещения. Обычно примитивные типы данных в модели EDM сопоставляются соответствующим примитивным типам данных в среде хранения или размещения. Сведения о том, как Entity Framework сопоставляют типы-примитивы в модели EDM с SQL Server типами данных, см. в разделе [SqlClient для Entity Framework](./ef/sqlclient-for-ef-types.md).  
  
> [!NOTE]
> Модель EDM не поддерживает коллекции примитивных типов данных.  
  
 Сведения о структурированных типах данных в модели EDM см. в разделе [тип сущности](entity-type.md) и [сложный тип](complex-type.md).  
  
## <a name="primitive-data-types-supported-in-the-entity-data-model"></a>Примитивные типы данных, поддерживаемые в модели EDM  

 В приведенной ниже таблице представлены примитивные типы данных, поддерживаемые моделью EDM. В таблице также перечислены [аспекты](facet.md) , которые можно применить к каждому примитивному типу данных.  
  
|Примитивный тип данных|Описание|Применимые аспекты|  
|-------------------------|-----------------|-----------------------|  
|Двоичные данные|Содержит двоичные данные.|MaxLength, FixedLength, Nullable, Default|  
|Логическое|Содержит значение `true` или `false`.|Nullable, Default|  
|Byte|Содержит 8-битное целое значение без знака.|Precision, Nullable, Default|  
|Дата и время|Представляет дату и время.|Precision, Nullable, Default|  
|DateTimeOffset|Возвращает дату и время в виде смещения в минутах от времени GMT.|Precision, Nullable, Default|  
|Decimal|Содержит точное числовое значение с заданной точностью и масштабом.|Precision, Nullable, Default|  
|Тип Double|Содержит число с плавающей запятой с точностью до 15 цифр.|Precision, Nullable, Default|  
|Float|Содержит число с плавающей запятой с точностью до 7 цифр.|Precision, Nullable, Default|  
|Guid|Содержит уникальный 16-битный идентификатор.|Precision, Nullable, Default|  
|Int16|Содержит 16-разрядное целое значение со знаком.|Precision, Nullable, Default|  
|Int32|Содержит 32-разрядное целое значение со знаком.|Precision, Nullable, Default|  
|Int64|Содержит 64-разрядное целое значение со знаком.|Precision, Nullable, Default|  
|SByte|Содержит 8-разрядное целое значение со знаком.|Precision, Nullable, Default|  
|Строка|Содержит символьные данные.|Unicode, FixedLength, MaxLength, Collation, Precision, Nullable, Default|  
|Time|Содержит время дня.|Precision, Nullable, Default|  
  
## <a name="see-also"></a>См. также раздел

- [Основные понятия модели EDM](entity-data-model-key-concepts.md)
- [EDM (модель данных с использованием сущностей)](entity-data-model.md)
