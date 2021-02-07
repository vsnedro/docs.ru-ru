---
description: Дополнительные сведения о свойстве внешнего ключа
title: свойство внешнего ключа
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: 1666e4477c09dd5d0ed3d2c35a93ca21824e8a0e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724132"
---
# <a name="foreign-key-property"></a>свойство внешнего ключа

*Свойство внешнего ключа* в EDM (EDM) является [свойством](property.md) типа-примитива (или набором свойств типа-примитива) для [типа сущности](entity-type.md) , который содержит [ключ сущности](entity-key.md) другого типа сущности.  
  
 Свойство внешнего ключа схоже со столбцом внешнего ключа в реляционной базе данных. Так же, как внешние ключевые столбцы используются в реляционной базе данных для создания связей между строками в таблицах, свойства внешнего ключа в концептуальной модели используются для установления [связей](association-type.md) между типами сущностей. [Ограничение ссылочной целостности](referential-integrity-constraint.md) используется для определения ассоциации между двумя типами сущностей, если один из типов имеет внешнее ключевое свойство.  
  
## <a name="example"></a>Пример  

 На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`. Тип сущности `Book` имеет свойство `PublisherId`, которое ссылается на ключ сущности типа сущности `Publisher` при определении ограничения ссылочной целостности ассоциации `PublishedBy`.  
  
 ![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "Пример модели ссылочного ограничения")  
  
 [Entity Framework ADO.NET](./ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), для определения концептуальных моделей. Следующий язык CSDL использует свойство внешнего ключа `PublisherId` для определения ограничения ссылочной целостности в ассоциации `PublishedBy`, приведенной ранее в концептуальной модели.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>См. также

- [Основные понятия модели EDM](entity-data-model-key-concepts.md)
- [EDM (модель данных с использованием сущностей)](entity-data-model.md)
