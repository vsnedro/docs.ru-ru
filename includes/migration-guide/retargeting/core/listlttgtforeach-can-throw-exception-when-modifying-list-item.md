---
ms.openlocfilehash: 3300a74b81fc9eeba670ee0ceb2c2615fd3925bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617284"
---
### <a name="listlttgtforeach-can-throw-exception-when-modifying-list-item"></a>List&lt;T&gt;.ForEach может создавать исключение при изменении элемента списка

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.5 перечислитель <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> будет создавать исключение <xref:System.InvalidOperationException?displayProperty=fullName> при изменении элемента в вызывающей коллекции. Ранее исключение не создавалось, но могли возникать конфликты.

#### <a name="suggestion"></a>Предложение

В идеальном случае следует исправить код, чтобы он не изменял списки при перечислении их элементов, поскольку эта операция небезопасна. Чтобы вернуться к предыдущему поведению, приложение должно быть предназначено для платформы .NET Framework 4.0.

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.5         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType>
