---
ms.openlocfilehash: de35df21d1887bc95a3106edba312c53daad8b68
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654746"
---
### <a name="netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5"></a>Символ препроцессора NETCOREAPP3_1 не определен при нацеливании на .NET 5

В .NET 5.0 RC2 и более поздних версиях в проектах больше не определяются символы препроцессора для более ранних версий. Определяются символы препроцессора только для целевой версии. Это то же самое поведение, что и в .NET Core 1.0–3.1.

#### <a name="version-introduced"></a>Представленная версия

5.0 RC2

#### <a name="change-description"></a>Описание изменений

В версиях .NET 5.0 с предварительной версии 7 до RC1 в проектах, предназначенных для `net5.0`, определяются символы препроцессора `NETCOREAPP3_1` и `NET5_0`. Цель этого изменения поведения заключается в том, чтобы начиная с .NET 5.0 символы условной компиляции [были накопительными](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).

В .NET 5.0 RC2 и более поздних версиях в проектах определяются только символы для моникеров целевой платформы (TFM), для которой она предназначена, а не для предыдущих версий.

#### <a name="reason-for-change"></a>Причина изменения

Изменение из предварительной версии 7 было отменено из-за отзывов пользователей. Определение символов для более ранних версий удивило и запутало пользователей, и некоторые предположили, что это ошибка в компиляторе C#.

#### <a name="recommended-action"></a>Рекомендованное действие

Убедитесь, что в логике `#if` не предполагается определение `NETCOREAPP3_1`, если проект предназначен для `net5.0` или более поздней версии. Вместо этого сделайте так, чтобы `NETCOREAPP3_1` определялся только в том случае, если проект явно предназначен для `netcoreapp3.1`.

Например, если проект предназначен для нескольких платформ (.NET Core 2.1 и .NET Core 3.1) и вы вызываете API, которые появились в .NET Core 3.1, то логика `#if` должна выглядеть следующим образом:

```csharp
#if NETCOREAPP2_1 || NETCOREAPP3_0
    // Fallback behavior for old versions.
#elif NETCOREAPP
    // Behavior for .NET Core 3.1 and later.
#endif
```

#### <a name="category"></a>Категория

MSBuild

#### <a name="affected-apis"></a>Затронутые API

Н/Д

<!--

#### Affected APIs

Not detectable via API analysis.

-->
