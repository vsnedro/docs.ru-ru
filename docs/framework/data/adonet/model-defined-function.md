---
description: 'Дополнительные сведения: определяемая моделью функция'
title: функция определенной модели
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 146ef4a8ad8c38897b8e56b6bc1485e1e40754cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723742"
---
# <a name="model-defined-function"></a>функция определенной модели

*Определяемая моделью функция* — это функция, определенная в концептуальной модели. Текст функции, определяемой моделью, выражается в [Entity SQL](./ef/language-reference/entity-sql-language.md), что позволяет выражать функцию независимо от правил или языков, поддерживаемых в источнике данных.  
  
 Определение определяемой моделью функции содержит следующие сведения.  
  
- Имя функции. (обязательно)  
  
- Тип возвращаемого значения. (необязательно)  
  
    > [!NOTE]
    > Если тип возвращаемого значения не задан, возвращаемого значения не будет.  
  
- Сведения о параметрах. (необязательно)  
  
- Выражение [Entity SQL](./ef/language-reference/entity-sql-language.md) , определяющее текст функции.  
  
 Обратите внимание, что определяемые моделью функции не поддерживают выходные параметры. Это ограничение введено, чтобы определяемые моделью функции можно было сочетать.  
  
## <a name="example"></a>Пример  

 На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.  
  
 ![Снимок экрана, на котором показана модель с опубликованной датой.](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 [Entity Framework ADO.NET](./ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), для определения концептуальных моделей. Следующий язык CSDL определяет функцию в концептуальной модели, которая возвращает числа лет с момента публикации экземпляра `Book` (ранее приведенного на схеме).  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a>См. также

- [Основные понятия модели EDM](entity-data-model-key-concepts.md)
- [EDM (модель данных с использованием сущностей)](entity-data-model.md)
- [EDM (модель данных с использованием сущностей): примитивные типы данных](entity-data-model-primitive-data-types.md)
