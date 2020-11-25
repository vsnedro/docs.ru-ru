---
title: Именование ресурсов
description: Ознакомьтесь с рекомендациями по именованию ресурсов в .NET, которые похожи на рекомендации по именованию свойств.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: 08046fb78638546b3dcab856674424c92c03fe83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706415"
---
# <a name="naming-resources"></a>Именование ресурсов

Так как на локализуемые ресурсы можно ссылаться через определенные объекты, как если бы они были свойствами, рекомендации по именованию ресурсов похожи на правила свойств.

 ✔️ использовать Паскалкасинг в ключах ресурсов.

 ✔️ предоставлять описательные, а не короткие идентификаторы.

 ❌ НЕ используйте ключевые слова, относящиеся к языку, для основных языков CLR.

 ✔️ использовать в качестве имен ресурсов только буквы, цифры и символы подчеркивания.

 ✔️ использовать следующее соглашение об именовании для ресурсов сообщений об исключениях.

 Идентификатор ресурса должен быть именем типа исключения и коротким идентификатором исключения:

 `ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`
 `ArgumentExceptionFileNameIsMalformed`

 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также раздел

- [Рекомендации по проектированию платформы](index.md)
- [Рекомендации по именованию](naming-guidelines.md)
