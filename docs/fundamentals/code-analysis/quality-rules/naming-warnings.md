---
title: Правила именования (анализ кода)
description: Сведения о правилах именования анализа кода.
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.namingrules
helpviewer_keywords:
- managed code analysis rules, naming rules
- naming rules
- rules, naming
author: gewarren
ms.author: gewarren
ms.openlocfilehash: 88e7ec6bc1051fa98c46696b2193a5d5912eb111
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592404"
---
# <a name="naming-rules"></a>Правила именования

Правила именования поддерживают соблюдение соглашений об именовании в рекомендациях по проектированию .NET.

## <a name="in-this-section"></a>В этом разделе

|Правило|Описание|
|----------|-----------------|
|[CA1700. Не присваивайте перечисляемым значениям имя Reserved](ca1700.md)|В данном правиле предполагается, что член перечисления, имя которого содержит слово "reserved", не используется в настоящее время, а является местозаполнителем, который будет в дальнейшем переименован или удален. Переименование или удаление элемента — это критическое изменение.|
|[CA1707. Идентификаторы не должны содержать символы подчеркивания](ca1707.md)|В соответствии с соглашением имена идентификаторов не могут содержать знак подчеркивания (_). Это правило позволяет проверить пространства имен, типы, элементы и параметры.|
|[CA1708. Идентификаторы должны отличаться не только прописными и строчными буквами](ca1708.md)|Идентификаторы пространств имен, типов, членов и параметров не могут отличаться только регистром знаков, поскольку языки программирования, поддерживаемые средой CLR, не обязательно учитывают регистр знаков.|
|[CA1710. Идентификаторы должны иметь правильные суффиксы](ca1710.md)|По соглашению имена типов, которые расширяют определенные базовые типы или реализуют определенные интерфейсы, или типы, производные от этих типов, имеют суффикс, связанный с базовым типом или интерфейсом.|
|[CA1711. Идентификаторы не должны иметь неправильные суффиксы](ca1711.md)|В соответствии с соглашением об именовании, определенные зарезервированные суффиксы должны добавляться только к именам типов, которые расширяют некоторые базовые типы или реализуют определенные интерфейсы, а также производных от них типов. В именах других типов зарезервированные суффиксы использоваться не должны.|
|[CA1712. Не добавляйте имя типа перед перечисляемыми значениями](ca1712.md)|Имена членов перечисления не имеют префикса с именем типа, так как ожидается, что информация о типах должна предоставляться средствами разработки.|
|[CA1713. События не должны иметь префикс before или after](ca1713.md)|Имя события начинается с Before или After. Чтобы дать имена связанным событиям, возникающим в определенной последовательности, используйте настоящее или прошедшее время, чтобы обозначить положение события в последовательности действий.|
|[CA1714. У перечислений флагов должны быть имена во множественном числе](ca1714.md)|Общее перечисление имеет атрибут System. FlagsAttribute и его имя не заканчивается на "s". Типы, помеченные как FlagsAttribute, имеют имена, которые являются во множественном числе, так как атрибут указывает, что может быть указано более одного значения.|
|[CA1715. Идентификаторы должны иметь правильные префиксы](ca1715.md)|Имя видимого извне интерфейса не начинается с заглавной буквы "I".  Имя параметра универсального типа для видимого извне типа или метода не начинается с заглавной буквы "T".|
|[CA1716. Идентификаторы не должны совпадать с ключевыми словами](ca1716.md)|Имя пространства имен или типа совпадает с ключевым словом, зарезервированным в языке программирования. Идентификаторы пространств имен и типов не должны совпадать с ключевыми словами, определенными в языках, поддерживаемых в среде CLR.|
|[CA1717. Только перечисления FlagsAttribute должны иметь имена во множественном числе](ca1717.md)|Согласно правилам именования множественное число имени перечисления указывает, что одновременно можно задать несколько значений перечисления.|
|[CA1720. Идентификаторы не должны содержать имена типов](ca1720.md)|Имя параметра в доступном для внешнего кода элементе содержит имя типа данных, или имя доступного для внешнего кода элемента содержит языковое имя типа данных.|
|[CA1721. Имена свойств не должны совпадать с именами методов get](ca1721.md)|Имя открытого или защищенного элемента начинается с Get и соответствует имени открытого или защищенного свойства и по другим параметрам. Методы Get и свойства должны иметь имена, позволяющие четко различать их функции.|
|[CA1724. Имена типов не должны совпадать с именами пространства имен](ca1724.md)|Имена типов не должны совпадать с именами пространств имен .NET. Нарушение этого правила может снизить удобство использования библиотеки.|
|[CA1725. Имена параметров должны соответствовать базовому объявлению](ca1725.md)|Согласованное именование параметров в иерархии переопределений увеличивает удобство использования переопределений метода. Если имя параметра в производном методе отличается от имени в базовом объявлении, может возникнуть путаница в определении того, чем является метод: переопределением базового метода или новой перегрузкой.|