---
title: Разработка с обеспечением расширяемости
ms.date: 10/22/2008
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: 9e75ef433f3bd9af34e8dd40331a8267755e59fe
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821389"
---
# <a name="designing-for-extensibility"></a>Разработка с обеспечением расширяемости
Одним из важных аспектов разработки платформы является обеспечение тщательного рассмотрения расширяемости платформы. Для этого необходимо понимать затраты и преимущества, связанные с различными механизмами расширения. Эта глава поможет вам решить, какие механизмы расширения (подклассы, события, виртуальные члены, обратные вызовы и т. д.) лучше удовлетворять требованиям вашей инфраструктуры.  
  
 Существует множество способов разрешить расширяемость в платформах. Они находятся в диапазоне от менее мощных, но менее дорогостоящих к очень мощным, но дорогостоящим. Для любого конкретного требования к расширяемости следует выбрать наиболее дорогостоящий механизм расширяемости, соответствующий требованиям. Помните, что обычно можно добавить дополнительную расширяемость, но вы никогда не сможете отказаться от внесения критических изменений.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Незапечатанные классы](unsealed-classes.md)  
 [Защищенные члены](protected-members.md)  
 [События и обратные вызовы](events-and-callbacks.md)  
 [Виртуальные члены](virtual-members.md)  
 [Абстракции (абстрактные типы и интерфейсы)](abstractions-abstract-types-and-interfaces.md)  
 [Базовые классы для реализации абстракций](base-classes-for-implementing-abstractions.md)  
 [Запечатывание](sealing.md)  
 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также статью

- [Рекомендации по проектированию платформы](index.md)
