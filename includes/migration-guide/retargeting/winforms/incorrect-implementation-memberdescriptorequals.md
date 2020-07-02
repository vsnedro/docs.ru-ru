---
ms.openlocfilehash: 2d0798917b639bc90bf3f78f6fb9f19d0eaf2c71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614818"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a>Неправильная реализация MemberDescriptor.Equals

#### <a name="details"></a>Подробнее

Исходная реализация метода <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> сравнивает два разных свойства строки из объектов для сравнения: имя категории и строка описания. Исправление заключается в сравнении <xref:System.ComponentModel.MemberDescriptor.Category> первого объекта с <xref:System.ComponentModel.MemberDescriptor.Category> второго объекта, и <xref:System.ComponentModel.MemberDescriptor.Description> первого объекта с <xref:System.ComponentModel.MemberDescriptor.Description> второго.

#### <a name="suggestion"></a>Предложение

Если приложение зависит от того, что <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> иногда возвращает значение `false`, когда дескрипторы эквивалентны, и вы используете .NET Framework 4.6.2 или более поздней версии, у вас есть несколько вариантов:

- Изменения в коде для сравнения полей <xref:System.ComponentModel.MemberDescriptor.Category> и <xref:System.ComponentModel.MemberDescriptor.Description> вручную в дополнение к вызову метода <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>.
- Откажитесь от этого изменения, добавив следующее значение в файл app.config:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />
</runtime>
```

Если ваше приложение предназначено для .NET Framework 4.6.1 или более ранней версии и выполняется на .NET Framework 4.6.2 или более поздней версии и вы хотите включить это изменение, вы можете указать для переключателя совместимости значение `false`, добавив следующее значение в файл app.config:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false" />
</runtime>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.6.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType>
