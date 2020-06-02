---
title: EDM (модель данных с использованием сущностей)
description: EDM описывает структуру данных независимо от их сохраненной формы, которая решает проблемы, связанные с сохранением данных во многих формах.
ms.date: 03/30/2017
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
ms.openlocfilehash: c98b1f4559ef297f8b11051940fd91f5f6fa06fd
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286744"
---
# <a name="entity-data-model"></a><span data-ttu-id="57019-103">EDM (модель данных с использованием сущностей)</span><span class="sxs-lookup"><span data-stu-id="57019-103">Entity Data Model</span></span>
<span data-ttu-id="57019-104">Модель EDM - это набор основных понятий, которые описывают структуру данных независимо от формы хранения.</span><span class="sxs-lookup"><span data-stu-id="57019-104">The Entity Data Model (EDM) is a set of concepts that describe the structure of data, regardless of its stored form.</span></span> <span data-ttu-id="57019-105">Модель EDM заимствует свойства модели «сущность-связь», описанной Питером Ченом в 1976 г., более того, она строится на модели «сущность-связь» и расширяет возможности ее традиционного использования.</span><span class="sxs-lookup"><span data-stu-id="57019-105">The EDM borrows from the Entity-Relationship Model described by Peter Chen in 1976, but it also builds on the Entity-Relationship Model and extends its traditional uses.</span></span>  
  
 <span data-ttu-id="57019-106">Модель EDM решает проблемы, возникающие из необходимости хранить данные в различных формах.</span><span class="sxs-lookup"><span data-stu-id="57019-106">The EDM addresses the challenges that arise from having data stored in many forms.</span></span> <span data-ttu-id="57019-107">Например, предположим, есть фирма, которая хранит данные в реляционных базах данных, текстовых файлах, файлах XML, электронных таблицах и отчетах.</span><span class="sxs-lookup"><span data-stu-id="57019-107">For example, consider a business that stores data in relational databases, text files, XML files, spreadsheets, and reports.</span></span> <span data-ttu-id="57019-108">Это является значительным препятствием для моделирования данных, проектирования приложений и доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="57019-108">This presents significant challenges in data modeling, application design, and data access.</span></span> <span data-ttu-id="57019-109">Во время проектирования приложения, ориентированного на работу с данными, сложность заключается в написании эффективного и поддерживаемого кода без ущерба для эффективности доступа к данным, хранения и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="57019-109">When designing a data-oriented application, the challenge is to write efficient and maintainable code without sacrificing efficient data access, storage, and scalability.</span></span> <span data-ttu-id="57019-110">Если данные имеют реляционную структуру, доступ к данным, хранение и масштабируемость будут весьма эффективными, однако написание эффективного и поддерживаемого кода становится более сложным.</span><span class="sxs-lookup"><span data-stu-id="57019-110">When data has a relational structure, data access, storage, and scalability are very efficient, but writing efficient and maintainable code becomes more difficult.</span></span> <span data-ttu-id="57019-111">Если данные имеют структуру объекта, компромиссы приобретают обратный характер: написание эффективного и поддерживаемого кода наносит ущерб эффективности доступа к данным, хранения и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="57019-111">When data has an object structure, the trade-offs are reversed: Writing efficient and maintainable code comes at the cost of efficient data access, storage, and scalability.</span></span> <span data-ttu-id="57019-112">Даже если для этих компромиссов будут найдены правильные решения, при перемещении данных из одной формы в другую возникают новые трудности.</span><span class="sxs-lookup"><span data-stu-id="57019-112">Even if the right balance between these trade-offs can be found, new challenges arise when data is moved from one form to another.</span></span> <span data-ttu-id="57019-113">Модель EDM решает эти трудности путем описания структуры данных на основе сущностей и связей, которые являются независимыми от схем хранения.</span><span class="sxs-lookup"><span data-stu-id="57019-113">The Entity Data Model addresses these challenges by describing the structure of data in terms of entities and relationships that are independent of any storage schema.</span></span> <span data-ttu-id="57019-114">В результате форма хранения данных уже не имеет отношения к проектированию приложений и разработке.</span><span class="sxs-lookup"><span data-stu-id="57019-114">This makes the stored form of data irrelevant to application design and development.</span></span> <span data-ttu-id="57019-115">Поскольку сущности и связи описывают структуру данных так, как она используется в приложении (а не ее форму хранения), они могут эволюционировать по мере эволюции приложения.</span><span class="sxs-lookup"><span data-stu-id="57019-115">And, because entities and relationships describe the structure of data as it is used in an application (not its stored form), they can evolve as an application evolves.</span></span>  
  
 <span data-ttu-id="57019-116">`conceptual model` - это специфическое представление структуры данных в виде сущностей и связей, которое обычно определяется на доменном языке DSL, реализующем основные понятия модели EDM.</span><span class="sxs-lookup"><span data-stu-id="57019-116">A `conceptual model` is a specific representation of the structure of data as entities and relationships, and is generally defined in a domain-specific language (DSL) that implements the concepts of the EDM.</span></span> <span data-ttu-id="57019-117">[Язык CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec) — это пример такого доменного языка.</span><span class="sxs-lookup"><span data-stu-id="57019-117">[Conceptual schema definition language (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec) is an example of such a domain-specific language.</span></span> <span data-ttu-id="57019-118">Сущности и связи, описанные в концептуальной модели, можно представить в виде абстракций объектов и ассоциаций в приложении.</span><span class="sxs-lookup"><span data-stu-id="57019-118">Entities and relationships described in a conceptual model can be thought of as abstractions of objects and associations in an application.</span></span> <span data-ttu-id="57019-119">Это позволяет разработчикам сфокусировать внимание на концептуальной модели, не думая о схеме хранения, и писать эффективный и поддерживаемый код.</span><span class="sxs-lookup"><span data-stu-id="57019-119">This allows developers to focus on the conceptual model without concern for the storage schema, and allows them to write code with efficiency and maintainability in mind.</span></span> <span data-ttu-id="57019-120">Одновременно разработчики схем хранения могут сфокусировать внимание на эффективности доступа к данным, хранения и масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="57019-120">Meanwhile storage schema designers can focus on the efficiency of data access, storage, and scalability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57019-121">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="57019-121">In This Section</span></span>  
 <span data-ttu-id="57019-122">В подразделах этого раздела описываются основные понятия модели EDM.</span><span class="sxs-lookup"><span data-stu-id="57019-122">Topics in this section describe the concepts of the Entity Data Model.</span></span> <span data-ttu-id="57019-123">Любой специфический язык домена (DSL), реализующий модель EDM, должен включать основные понятия, описанные в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="57019-123">Any DSL that implements the EDM should include the concepts described here.</span></span> <span data-ttu-id="57019-124">Обратите внимание, что [ADO.NET Entity Framework](./ef/index.md) использует язык CSDL для определения концептуальных моделей.</span><span class="sxs-lookup"><span data-stu-id="57019-124">Note that the [ADO.NET Entity Framework](./ef/index.md) uses CSDL to define conceptual models.</span></span> <span data-ttu-id="57019-125">Для получения дополнительной информации см. [CSDL Specification](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).</span><span class="sxs-lookup"><span data-stu-id="57019-125">For more information, see [CSDL Specification](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).</span></span>  
  
 [<span data-ttu-id="57019-126">Основные понятия модели EDM</span><span class="sxs-lookup"><span data-stu-id="57019-126">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)  
  
 [<span data-ttu-id="57019-127">EDM (модель данных с использованием сущностей): Пространства имен</span><span class="sxs-lookup"><span data-stu-id="57019-127">Entity Data Model: Namespaces</span></span>](entity-data-model-namespaces.md)  
  
 [<span data-ttu-id="57019-128">EDM (модель данных с использованием сущностей): примитивные типы данных</span><span class="sxs-lookup"><span data-stu-id="57019-128">Entity Data Model: Primitive Data Types</span></span>](entity-data-model-primitive-data-types.md)  
  
 [<span data-ttu-id="57019-129">EDM (модель данных с использованием сущностей): Наследование</span><span class="sxs-lookup"><span data-stu-id="57019-129">Entity Data Model: Inheritance</span></span>](entity-data-model-inheritance.md)  
  
 [<span data-ttu-id="57019-130">конечная точка ассоциации</span><span class="sxs-lookup"><span data-stu-id="57019-130">association end</span></span>](association-end.md)  
  
 [<span data-ttu-id="57019-131">кратность конечной точки ассоциации</span><span class="sxs-lookup"><span data-stu-id="57019-131">association end multiplicity</span></span>](association-end-multiplicity.md)  
  
 [<span data-ttu-id="57019-132">набор ассоциаций</span><span class="sxs-lookup"><span data-stu-id="57019-132">association set</span></span>](association-set.md)  
  
 [<span data-ttu-id="57019-133">конечная точка набора ассоциаций</span><span class="sxs-lookup"><span data-stu-id="57019-133">association set end</span></span>](association-set-end.md)  
  
 [<span data-ttu-id="57019-134">тип ассоциации</span><span class="sxs-lookup"><span data-stu-id="57019-134">association type</span></span>](association-type.md)  
  
 [<span data-ttu-id="57019-135">сложный тип</span><span class="sxs-lookup"><span data-stu-id="57019-135">complex type</span></span>](complex-type.md)  
  
 [<span data-ttu-id="57019-136">контейнер сущностей</span><span class="sxs-lookup"><span data-stu-id="57019-136">entity container</span></span>](entity-container.md)  
  
 [<span data-ttu-id="57019-137">ключ сущности</span><span class="sxs-lookup"><span data-stu-id="57019-137">entity key</span></span>](entity-key.md)  
  
 [<span data-ttu-id="57019-138">набор сущностей</span><span class="sxs-lookup"><span data-stu-id="57019-138">entity set</span></span>](entity-set.md)  
  
 [<span data-ttu-id="57019-139">тип сущности</span><span class="sxs-lookup"><span data-stu-id="57019-139">entity type</span></span>](entity-type.md)  
  
 [<span data-ttu-id="57019-140">устанавливают</span><span class="sxs-lookup"><span data-stu-id="57019-140">facet</span></span>](facet.md)  
  
 [<span data-ttu-id="57019-141">свойство внешнего ключа</span><span class="sxs-lookup"><span data-stu-id="57019-141">foreign key property</span></span>](foreign-key-property.md)  
  
 [<span data-ttu-id="57019-142">объявляемая моделью функция</span><span class="sxs-lookup"><span data-stu-id="57019-142">model-declared function</span></span>](model-declared-function.md)  
  
 [<span data-ttu-id="57019-143">функция определенной модели</span><span class="sxs-lookup"><span data-stu-id="57019-143">model-defined function</span></span>](model-defined-function.md)  
  
 [<span data-ttu-id="57019-144">свойство навигации</span><span class="sxs-lookup"><span data-stu-id="57019-144">navigation property</span></span>](navigation-property.md)  
  
 [<span data-ttu-id="57019-145">property</span><span class="sxs-lookup"><span data-stu-id="57019-145">property</span></span>](property.md)  
  
 [<span data-ttu-id="57019-146">ограничение ссылочной целостности</span><span class="sxs-lookup"><span data-stu-id="57019-146">referential integrity constraint</span></span>](referential-integrity-constraint.md)  
  
## <a name="see-also"></a><span data-ttu-id="57019-147">См. также</span><span class="sxs-lookup"><span data-stu-id="57019-147">See also</span></span>

- <span data-ttu-id="57019-148">[Средства EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="57019-148">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="57019-149">[Общие сведения о EDMX-файлах](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="57019-149">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="57019-150">Спецификация языка CSDL</span><span class="sxs-lookup"><span data-stu-id="57019-150">CSDL Specification</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
