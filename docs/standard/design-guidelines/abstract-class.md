---
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
ms.openlocfilehash: 6903e10c8695376d8ac5961461796c5413307f90
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821649"
---
# <a name="abstract-class-design"></a>Разработка абстрактных классов

❌ НЕ определяйте открытые или защищенные внутренние конструкторы в абстрактных типах.

 Конструкторы должны быть открытыми только в том случае, если пользователям необходимо создавать экземпляры типа. Поскольку нельзя создавать экземпляры абстрактного типа, абстрактный тип с открытым конструктором неверно спроектирован и ошибочно ведет себя для пользователей.

 ✔️ определить защищенный или внутренний конструктор в абстрактных классах.

 Защищенный конструктор является более распространенным и просто позволяет базовому классу выполнять собственную инициализацию при создании подтипов.

 Внутренний конструктор можно использовать для ограничения конкретных реализаций абстрактного класса сборкой, определяющей класс.

 ✔️ предоставить по крайней мере один конкретный тип, наследующий от каждого передаваемого абстрактного класса.

 Это помогает проверить структуру абстрактного класса. Например,  <xref:System.IO.FileStream?displayProperty=nameWithType> является реализацией <xref:System.IO.Stream?displayProperty=nameWithType> абстрактного класса.

 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также статью

- [Рекомендации по проектированию типов](type.md)
- [Рекомендации по проектированию платформы](index.md)
