---
title: тип сущности
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 3f99667a06d8aa439232802d4909290dfe9db97c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194782"
---
# <a name="entity-type"></a><span data-ttu-id="45371-102">тип сущности</span><span class="sxs-lookup"><span data-stu-id="45371-102">entity type</span></span>

<span data-ttu-id="45371-103">*Тип сущности* является фундаментальным стандартным блоком для описания структуры данных с помощью EDM (EDM).</span><span class="sxs-lookup"><span data-stu-id="45371-103">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="45371-104">В концептуальной модели тип сущности представляет структуру основных концептуальных элементов верхнего уровня, таких как клиенты или заказы.</span><span class="sxs-lookup"><span data-stu-id="45371-104">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="45371-105">Тип сущности - это шаблон для экземпляров типов сущностей.</span><span class="sxs-lookup"><span data-stu-id="45371-105">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="45371-106">Каждый шаблон содержит следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="45371-106">Each template contains the following information:</span></span>  
  
- <span data-ttu-id="45371-107">Уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="45371-107">A unique name.</span></span> <span data-ttu-id="45371-108">(Обязательно).</span><span class="sxs-lookup"><span data-stu-id="45371-108">(Required.)</span></span>  
  
- <span data-ttu-id="45371-109">[Ключ сущности](entity-key.md) , определенный одним или несколькими свойствами.</span><span class="sxs-lookup"><span data-stu-id="45371-109">An [entity key](entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="45371-110">(Обязательно).</span><span class="sxs-lookup"><span data-stu-id="45371-110">(Required.)</span></span>  
  
- <span data-ttu-id="45371-111">Данные в виде [свойств](property.md).</span><span class="sxs-lookup"><span data-stu-id="45371-111">Data in the form of [properties](property.md).</span></span> <span data-ttu-id="45371-112">(Необязательно.)</span><span class="sxs-lookup"><span data-stu-id="45371-112">(Optional.)</span></span>  
  
- <span data-ttu-id="45371-113">[Свойства навигации](navigation-property.md) , позволяющие переходить с одного [конца](association-end.md) [ассоциации](association-type.md) на другой конец.</span><span class="sxs-lookup"><span data-stu-id="45371-113">[Navigation properties](navigation-property.md) that allow for navigation from one [end](association-end.md) of an [association](association-type.md) to the other end.</span></span> <span data-ttu-id="45371-114">(необязательно)</span><span class="sxs-lookup"><span data-stu-id="45371-114">(Optional)</span></span>  
  
 <span data-ttu-id="45371-115">В приложении экземпляр типа сущности представляет определенный объект (например, определенного клиента или заказ).</span><span class="sxs-lookup"><span data-stu-id="45371-115">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="45371-116">Каждый экземпляр типа сущности должен иметь уникальный [ключ сущности](entity-key.md) в [наборе сущностей](entity-set.md).</span><span class="sxs-lookup"><span data-stu-id="45371-116">Each instance of an entity type must have a unique [entity key](entity-key.md) within an [entity set](entity-set.md).</span></span>  
  
 <span data-ttu-id="45371-117">Два экземпляра типа сущности считаются равными, только если они являются экземплярами одного типа и значения их ключей сущности равны.</span><span class="sxs-lookup"><span data-stu-id="45371-117">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45371-118">Пример</span><span class="sxs-lookup"><span data-stu-id="45371-118">Example</span></span>  

 <span data-ttu-id="45371-119">На приведенной ниже схеме показана концептуальная модель с тремя типами сущностей: `Book`, `Publisher` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="45371-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 ![Пример модели с тремя типами сущностей](./media/entity-type/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="45371-121">Обратите внимание, что свойства каждого типа сущности, составляющего его ключ сущности, обозначаются знаком «(Ключ)».</span><span class="sxs-lookup"><span data-stu-id="45371-121">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="45371-122">[Entity Framework ADO.NET](./ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="45371-122">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="45371-123">Ниже на языке CSDL определяется тип сущности `Book`, который ранее приводился в схеме.</span><span class="sxs-lookup"><span data-stu-id="45371-123">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="45371-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="45371-124">See also</span></span>

- [<span data-ttu-id="45371-125">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="45371-125">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="45371-126">EDM (модель данных с использованием сущностей)</span><span class="sxs-lookup"><span data-stu-id="45371-126">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="45371-127">устанавливают</span><span class="sxs-lookup"><span data-stu-id="45371-127">facet</span></span>](facet.md)
