---
title: Правила, касающиеся ненужного кода
description: Дополнительные сведения о ненужных правилах кода для анализа кода
ms.date: 09/30/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
ms.openlocfilehash: 16c4ba0e4bee2388736bf9813a3e8290d8d4da32
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "96593858"
---
# <a name="unnecessary-code-rules"></a>Правила, касающиеся ненужного кода

Ненужные правила кода определяют различные части базы кода, которые не нужны и могут быть подвергнуты рефакторингу или удалению. Наличие ненужного кода указывает на одну из следующих проблем:

- Удобочитаемость: код, который необязательно ухудшает читаемость. Например, [IDE0001](ide0001.md) помечает ненужные квалификации типа Name.
- Удобство сопровождения: код, который больше не используется после рефакторинга и необязательно обслуживается. Например, [IDE0051](ide0051.md) помечает неиспользуемые закрытые поля, свойства, события и методы.
- Производительность: ненужные вычисления, не имеющие побочных эффектов и ведущие к ненужным издержкам на производительность. Например, [IDE0059](ide0059.md) помечает неиспользуемые назначения значений, когда выражение для расчета значения не имеет побочных эффектов.
- Функциональность: функциональная ошибка в коде, ведущая к требуемому коду, который подготавливается к просмотру избыточным. Например, [IDE0060](ide0060.md) помечает неиспользуемые параметры, когда метод случайно игнорирует входной параметр.

Правила в этом разделе касаются следующих ненужных правил кода:

- [Упростите имя (IDE0001)](ide0001.md)
- [Упрощение доступа к членам (IDE0002)](ide0002.md)
- [Удалить ненужное приведение (IDE0004)](ide0004.md)
- [Удалить ненужный импорт (IDE0005)](ide0005.md)
- [Удаление недостижимого кода (IDE0035)](ide0035.md)
- [Удалить неиспользуемый частный член (IDE0051)](ide0051.md)
- [Удалить непрочтенный частный член (IDE0052)](ide0052.md)
- [Удалить неиспользуемое значение выражения (IDE0058)](ide0058.md)
- [Удалить ненужное назначение значения (IDE0059)](ide0059.md)
- [Удалить неиспользуемый параметр (IDE0060)](ide0060.md)
- [Удалить ненужное подавление (IDE0079)](ide0079.md)
- [Удалить ненужный оператор подавления (IDE0080)](ide0080.md) — только C#.
- [Удалить "ByVal" (IDE0081)](ide0081.md) — только Visual Basic.
- [Удалить ненужный оператор равенства (IDE0100)](ide0100.md)
- [Удалите ненужный отказ (IDE0110)](ide0110.md) — только C#.

Некоторые из этих правил имеют параметры для настройки поведения правила.

- [csharp_style_unused_value_expression_statement_preference (IDE0058)](ide0058.md#csharp_style_unused_value_expression_statement_preference)
- [visual_basic_style_unused_value_expression_statement_preference (IDE0058)](ide0058.md#visual_basic_style_unused_value_expression_statement_preference)
- [csharp_style_unused_value_assignment_preference (IDE0059)](ide0059.md#csharp_style_unused_value_assignment_preference)
- [visual_basic_style_unused_value_assignment_preference (IDE0059)](ide0059.md#visual_basic_style_unused_value_assignment_preference)
- [dotnet_code_quality_unused_parameters (IDE0060)](ide0060.md#dotnet_code_quality_unused_parameters)
- [dotnet_remove_unnecessary_suppression_exclusions (IDE0079)](ide0079.md#dotnet_remove_unnecessary_suppression_exclusions)

## <a name="see-also"></a>См. также

- [Правила языка для стиля кода](language-rules.md)
- [Справочник по правилам стиля кода](index.md)
