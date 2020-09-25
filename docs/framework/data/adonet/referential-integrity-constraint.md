---
title: ограничение ссылочной целостности
description: Сведения об ограничениях ссылочной целостности в EDM, которые гарантируют, что между типами сущностей всегда существуют допустимые ассоциации.
ms.date: 03/30/2017
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
ms.openlocfilehash: 6ade9d0155a6915757c7f47c5cb3ab0a51dbd437
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172740"
---
# <a name="referential-integrity-constraint"></a><span data-ttu-id="947f4-103">ограничение ссылочной целостности</span><span class="sxs-lookup"><span data-stu-id="947f4-103">referential integrity constraint</span></span>

<span data-ttu-id="947f4-104">*Ограничение ссылочной целостности* в EDM (EDM) аналогично ограничению ссылочной целостности в реляционной базе данных.</span><span class="sxs-lookup"><span data-stu-id="947f4-104">A *referential integrity constraint* in the Entity Data Model (EDM) is similar to a referential integrity constraint in a relational database.</span></span> <span data-ttu-id="947f4-105">Точно так же, как столбец (или столбцы) из таблицы базы данных может ссылаться на первичный ключ другой таблицы, [свойство](property.md) (или свойства) [типа сущности](entity-type.md) может ссылаться на [ключ сущности](entity-key.md) другого типа сущности.</span><span class="sxs-lookup"><span data-stu-id="947f4-105">In the same way that a column (or columns) from a database table can reference the primary key of another table, a [property](property.md) (or properties) of an [entity type](entity-type.md) can reference the [entity key](entity-key.md) of another entity type.</span></span> <span data-ttu-id="947f4-106">Тип сущности, на который указывает ссылка, называется *основным элементом* ограничения.</span><span class="sxs-lookup"><span data-stu-id="947f4-106">The entity type that is referenced is called the *principal end* of the constraint.</span></span> <span data-ttu-id="947f4-107">Тип сущности, который ссылается на основной элемент, называется *зависимым окончанием* ограничения.</span><span class="sxs-lookup"><span data-stu-id="947f4-107">The entity type that references the principal end is called the *dependent end* of the constraint.</span></span>  
  
 <span data-ttu-id="947f4-108">Ограничение ссылочной целостности определяется как часть [связи](association-type.md) между двумя типами сущностей.</span><span class="sxs-lookup"><span data-stu-id="947f4-108">A referential integrity constraint is defined as part of an [association](association-type.md) between two entity types.</span></span> <span data-ttu-id="947f4-109">Определение ограничения ссылочной целостности включает следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="947f4-109">The definition for a referential integrity constraint specifies the following information:</span></span>  
  
- <span data-ttu-id="947f4-110">Основной конец ограничения.</span><span class="sxs-lookup"><span data-stu-id="947f4-110">The principal end of the constraint.</span></span> <span data-ttu-id="947f4-111">(Тип сущности, ключ сущности которого имеет ссылку на зависимый конец.)</span><span class="sxs-lookup"><span data-stu-id="947f4-111">(An entity type whose entity key is referenced by the dependent end.)</span></span>  
  
- <span data-ttu-id="947f4-112">Ключ сущности основного конца.</span><span class="sxs-lookup"><span data-stu-id="947f4-112">The entity key of the principal end.</span></span>  
  
- <span data-ttu-id="947f4-113">Зависимый конец ограничения.</span><span class="sxs-lookup"><span data-stu-id="947f4-113">The dependent end of the constraint.</span></span> <span data-ttu-id="947f4-114">(Тип сущности, который имеет свойство или свойства, ссылающиеся на ключ сущности основного конца.)</span><span class="sxs-lookup"><span data-stu-id="947f4-114">(An entity type that has a property or properties that reference the entity key of the principal end.)</span></span>  
  
- <span data-ttu-id="947f4-115">Ссылка на свойство или свойства зависимого конца.</span><span class="sxs-lookup"><span data-stu-id="947f4-115">The referencing property or properties of the dependent end.</span></span>  
  
 <span data-ttu-id="947f4-116">Целью ограничения ссылочной целостности в модели EDM является обеспечение постоянного существования допустимых ассоциаций.</span><span class="sxs-lookup"><span data-stu-id="947f4-116">The purpose of referential integrity constraints in the EDM is to ensure that valid associations always exist.</span></span> <span data-ttu-id="947f4-117">Дополнительные сведения см. в разделе [свойство внешнего ключа](foreign-key-property.md).</span><span class="sxs-lookup"><span data-stu-id="947f4-117">For more information, see [foreign key property](foreign-key-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="947f4-118">Пример</span><span class="sxs-lookup"><span data-stu-id="947f4-118">Example</span></span>  

 <span data-ttu-id="947f4-119">На приведенной ниже схеме показана концептуальная модель с двумя ассоциациями: `WrittenBy` и `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="947f4-119">The diagram below shows a conceptual model with two associations: `WrittenBy` and `PublishedBy`.</span></span> <span data-ttu-id="947f4-120">Тип сущности `Book` имеет свойство `PublisherId`, которое ссылается на ключ сущности типа сущности `Publisher` при определении ограничения ссылочной целостности ассоциации `PublishedBy`.</span><span class="sxs-lookup"><span data-stu-id="947f4-120">The `Book` entity type has a property, `PublisherId`, that references the entity key of the `Publisher` entity type when you define a referential integrity constraint on the `PublishedBy` association.</span></span>  
  
 <span data-ttu-id="947f4-121">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "Пример модели ссылочного ограничения")</span><span class="sxs-lookup"><span data-stu-id="947f4-121">![RefConstraintModel](./media/referential-integrity-constraint/reference-constraint-model.gif "Example of a referential constraint model")</span></span>  
  
 <span data-ttu-id="947f4-122">[Entity Framework ADO.NET](./ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="947f4-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="947f4-123">Далее на языке CSDL определяется ограничение ссылочной целостности для ассоциации `PublishedBy`, которая ранее приводилась в концептуальной модели.</span><span class="sxs-lookup"><span data-stu-id="947f4-123">The following CSDL defines a referential integrity constraint on the `PublishedBy` association shown in the conceptual model above.</span></span>  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a><span data-ttu-id="947f4-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="947f4-124">See also</span></span>

- [<span data-ttu-id="947f4-125">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="947f4-125">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="947f4-126">EDM (модель данных с использованием сущностей)</span><span class="sxs-lookup"><span data-stu-id="947f4-126">Entity Data Model</span></span>](entity-data-model.md)
