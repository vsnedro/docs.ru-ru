---
description: 'Дополнительные сведения о: EDM: пространства имен'
title: 'EDM (модель данных с использованием сущностей): Пространства имен'
ms.date: 03/30/2017
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
ms.openlocfilehash: c18178672ebab0e323c9712af2668c3cb92e0300
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672768"
---
# <a name="entity-data-model-namespaces"></a>EDM (модель данных с использованием сущностей): Пространства имен

Пространство имен в EDM (EDM) является абстрактным контейнером для [типов сущностей](entity-type.md), [сложных типов](complex-type.md)и [ассоциаций](association-type.md). Пространства имен в модели EDM схожи с пространствами имен в языке программирования: они обеспечивают контекст для объектов, которые они содержат, а также являются способом устранения неопределенности в отношении объектов, которые имеют одно и то же имя (но содержатся в разных пространствах имен).  
  
## <a name="example"></a>Пример  

 [Entity Framework ADO.NET](./ef/index.md) использует доменный язык (DSL), называемый языком определения концептуальной схемы ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), для определения концептуальных моделей. В следующем коде на языке CSDL используется пространство имен для идентификации типа, определенного в другой концептуальной модели. В примере определяется тип сущности (`Publisher`), который имеет свойство сложного типа (`Address`), импортированного из пространства имен `ExtendedBooksModel`. Обратите внимание, что элемент `Using` указывает на то, что пространство имен было импортировано. Также обратите внимание, что тип свойства `Address` определен при помощи своего полного имени (`ExtendedBooksModel.Address`) с указанием на то, что этот тип определен в пространстве имен `ExtendedBooksModel`.  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a>См. также

- [Основные понятия модели EDM](entity-data-model-key-concepts.md)
- [EDM (модель данных с использованием сущностей)](entity-data-model.md)
