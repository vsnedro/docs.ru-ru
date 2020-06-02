---
title: Правила разработки членов
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
ms.openlocfilehash: c323e7edd752a1f003bd3f5d81689aca0eaefd20
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288996"
---
# <a name="member-design-guidelines"></a>Правила разработки членов
Методы, свойства, события, конструкторы и поля вместе называются членами. Члены в конечном итоге представляют собой средства, с помощью которых функциональные возможности платформы предоставляются конечным пользователям платформы.  
  
 Члены могут быть виртуальными или невиртуальными, конкретными или абстрактными, статическими или экземплярами, а также могут иметь несколько различных областей доступа. Все эти разнообразные выявляются невероятно выразительным, но в то же время необходимо соблюдать часть конструктора инфраструктуры.  
  
 Эта глава содержит основные рекомендации, которые следует выполнить при проектировании элементов любого типа.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Перегрузка членов](member-overloading.md)  
 [Конструктор свойств](property.md)  
 [Конструктор конструктора](constructor.md)  
 [Проектирование событий](event.md)  
 [Проектирование полей](field.md)  
 [Методы расширения](extension-methods.md)  
 [Перегрузки операторов](operator-overloads.md)  
 [Конструктор параметров](parameter-design.md)  
 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию платформы](index.md)
