---
description: 'Узнайте подробнее о: Разработка абстрактных классов'
title: Разработка абстрактных классов
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
ms.openlocfilehash: 5b1cd833bf43e5bf5731176243809393187e84d4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642465"
---
# <a name="abstract-class-design"></a>Разработка абстрактных классов

❌ НЕ СЛЕДУЕТ определять открытые или защищенные внутренние конструкторы в абстрактных типах.

 Конструкторы должны быть открытыми только в том случае, если пользователям необходимо создавать экземпляры заданного типа. Так как невозможно создавать экземпляры абстрактного типа, абстрактный тип с открытым конструктором является недопустимым и вводит пользователей в заблуждение.

 ✔️ СЛЕДУЕТ определять защищенный или внутренний конструктор в абстрактных классах.

 Защищенные конструкторы более популярны и просто разрешают базовому классу выполнять собственную инициализацию при создании подтипов.

 Внутренний конструктор можно использовать для ограничения конкретных реализаций абстрактного класса сборкой, определяющей класс.

 ✔️ СЛЕДУЕТ предоставить по крайней мере один конкретный тип, наследующий от каждого передаваемого абстрактного класса.

 Это помогает проверить структуру абстрактного класса. Например, <xref:System.IO.FileStream?displayProperty=nameWithType> является реализацией абстрактного класса <xref:System.IO.Stream?displayProperty=nameWithType>.

 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также

- [Рекомендации по разработке типов](type.md)
- [Рекомендации по проектированию на основе Framework](index.md)
