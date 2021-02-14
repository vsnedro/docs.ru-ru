---
description: 'Узнайте подробнее о: Разработка с обеспечением расширяемости'
title: Разработка с обеспечением расширяемости
ms.date: 10/22/2008
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: 148ae25380698a5a1161fb9fbdd3cc60102e865d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642270"
---
# <a name="designing-for-extensibility"></a>Разработка с обеспечением расширяемости

Один важный аспект разработки платформы заключается в уделении пристального внимания расширяемости платформы. Для этого вы должны знать о затратах и преимуществах, которые связаны с разными механизмами расширяемости. Приведенные в этой главе сведения помогут вам подобрать оптимальный механизм расширяемости — создание подклассов, события, виртуальные члены, обратные вызовы и т. д. — для удовлетворения требований вашей платформы.  
  
 Существует множество способов реализовать расширяемость на платформах. Они могут быть как менее эффективными, но и более экономичными, так и очень эффективными и затратными. Для удовлетворения требований к расширяемости при возможности выбирайте такой механизм, который связан с минимальными затратами. Помните, что обычно вы можете без проблем повысить уровень расширяемости, но его понижение требует кардинальных изменений.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Незапечатанные классы](unsealed-classes.md)  
 [Защищенные члены](protected-members.md)  
 [События и обратные вызовы](events-and-callbacks.md)  
 [Виртуальные члены](virtual-members.md)  
 [Абстракции (абстрактные типы и интерфейсы)](abstractions-abstract-types-and-interfaces.md)  
 [Базовые классы для реализации абстракций](base-classes-for-implementing-abstractions.md)  
 [Запечатывание](sealing.md)  
 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](index.md)
