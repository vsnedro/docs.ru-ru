---
title: 'Зарезервированные атрибуты C#: Conditional, Obsolete, AttributeUsage'
ms.date: 04/09/2020
description: Компилятор интерпретирует эти атрибуты, чтобы они могли влиять на создаваемый им код.
ms.openlocfilehash: c6d697dd08233ffc88900949998047137ee170a9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/29/2020
ms.locfileid: "82021765"
---
# <a name="reserved-attributes-conditionalattribute-obsoleteattribute-attributeusageattribute"></a>Зарезервированные атрибуты: ConditionalAttribute, ObsoleteAttribute, AttributeUsageAttribute

Эти атрибуты можно применять к элементам в коде. Они добавляют к ним семантическое значение. Компилятор использует эти семантические значения для изменения выходных данных и сообщения о возможных ошибках разработчиков, использующих код.

## <a name="conditional-attribute"></a>Атрибут `Conditional`

Атрибут `Conditional` определяет зависимость выполнения метода от идентификатора предварительной обработки. Атрибут `Conditional` является псевдонимом для <xref:System.Diagnostics.ConditionalAttribute> и может применяться к методу или классу атрибута.

В следующем примере атрибут `Conditional` применяется к методу для включения и отключения отображения диагностической информации для конкретной программы.

:::code language="csharp" source="snippets/trace.cs" interactive="try-dotnet" :::

Если идентификатор `TRACE_ON` не определен, выходные данные трассировки не отображаются. Поэкспериментируйте в интерактивном окне.

Атрибут `Conditional` часто используется с идентификатором `DEBUG` для включения функций трассировки и ведения журнала для отладочных сборок (но не сборок выпуска), как показано в следующем примере.

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditional" :::

Когда вызывается метод, помеченный как условный, наличие или отсутствие заданного символа предварительной обработки определяет, включается вызов или пропускается. Если этот символ определен, вызов включается; в противном случае вызов пропускается. Условный метод должен быть методом в объявлении класса или структуры и должен иметь тип возвращаемого значения `void`. Использование атрибута `Conditional` — это более понятная, элегантная и менее подверженная ошибкам альтернатива вложению методов в блоки `#if…#endif`.

Если метод содержит несколько атрибутов `Conditional`, вызов метода включается, если определен один условный символ или несколько (символы логически связаны с помощью оператора ИЛИ). В следующем примере наличие `A` или `B` приведет к вызову метода.

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetMultipleConditions" :::

### <a name="using-conditional-with-attribute-classes"></a>Использование `Conditional` с классами атрибутов

Атрибут `Conditional` также может применяться к определению класса атрибута. В следующем примере настраиваемый атрибут `Documentation` добавит сведения в метаданные, только если задано значение `DEBUG`.

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditionalConditionalAttribute" :::

## <a name="obsolete-attribute"></a>Атрибут `Obsolete`

Атрибут `Obsolete` помечает элемент кода как больше не рекомендуемый для использования. Использование сущности, помеченной как устаревшая, приводит к возникновению предупреждения или ошибки. Атрибут `Obsolete` является атрибутом однократного использования и может применяться к любой сущности, допускающей использование атрибутов. `Obsolete` является псевдонимом для <xref:System.ObsoleteAttribute>.

В следующем примере атрибут `Obsolete` применяется к классу `A` и к методу `B.OldMethod`. Поскольку для второго аргумента конструктора атрибутов, примененного к `B.OldMethod`, задано значение `true`, этот метод будет вызывать ошибку компилятора, тогда как при использовании класса `A` будет просто создаваться предупреждение. При этом вызов `B.NewMethod` не создает предупреждений или ошибок. Например, при использовании с предыдущими определениями следующий код создает два предупреждения и одну ошибку:

:::code language="csharp" source="snippets/ObsoleteExample.cs" interactive="try-dotnet" :::

Строка, предоставленная в качестве первого аргумента конструктору атрибута, будет отображаться как часть предупреждения или ошибки. Создается два предупреждения для класса `A`: одно для объявления ссылки на класс, а второе — для конструктора класса. Атрибут `Obsolete` может использоваться без аргументов, однако рекомендуется включать пояснение о том, что следует использовать вместо него.

## <a name="attributeusage-attribute"></a>Атрибут `AttributeUsage`

Атрибут `AttributeUsage` определяет, как можно использовать пользовательский класс атрибутов. <xref:System.AttributeUsageAttribute> — это атрибут, примененный к определениям настраиваемого атрибута. С помощью атрибута `AttributeUsage` можно контролировать:

- Какой атрибут элементов программы можно применить. Если вы не ограничите использование, атрибут можно применить к любому из следующих элементов программы:
  - сборка
  - module
  - поле
  - event
  - method
  - param
  - свойство;
  - return
  - type
- Можно ли применить атрибут к одному элементу программы несколько раз.
- Могут ли атрибуты наследоваться производными классами.

При явном применении параметры по умолчанию выглядят следующим образом:

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageFirst" :::

В этом примере класс `NewAttribute` можно применить к любому поддерживаемому элементу программы. Но он применяется к каждому объекту только один раз. Атрибут наследуется производными классами при применении к базовому классу.

Аргументы <xref:System.AttributeUsageAttribute.AllowMultiple> и <xref:System.AttributeUsageAttribute.Inherited> являются необязательными, так что следующий код имеет тот же результат:

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageSecond" :::

Первый аргумент <xref:System.AttributeUsageAttribute> должен состоять из одного или нескольких элементов перечисления <xref:System.AttributeTargets>. Несколько типов целевого объекта можно связать с помощью оператора OR, как показано в следующем примере:

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetDefinePropertyAttribute" :::

Начиная с C# 7.3 атрибуты могут применяться либо к свойству, либо к резервному полю для автоматически реализуемого свойства. Атрибут применяется к свойству, если не указан описатель `field` для атрибута. Оба случая показаны в следующем примере:

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetUsePropertyAttribute" :::

Если аргументу <xref:System.AttributeUsageAttribute.AllowMultiple> присвоено значение `true`, то результирующий атрибут можно применить несколько раз к одной сущности, как показано в следующем примере:

:::code language="csharp" source="snippets/MultiUseAttribute.cs" id="SnippetMultiUse" :::

В этом случае `MultiUseAttribute` можно применять несколько раз, так как `AllowMultiple` имеет значение `true`. Для применения нескольких атрибутов допускаются оба показанных формата.

Если <xref:System.AttributeUsageAttribute.Inherited> — `false`, атрибут не наследуется классами, производными от класса атрибутов. Пример:

:::code language="csharp" source="snippets/NonInheritedAttribute.cs" id="SnippetNonInherited" :::

В этом случае `NonInheritedAttribute` не применяется к `DClass` путем наследования.

## <a name="see-also"></a>См. также

- <xref:System.Attribute>
- <xref:System.Reflection>
- [Атрибуты](../../../standard/attributes/index.md)
- [Отражение](../../programming-guide/concepts/reflection.md)
