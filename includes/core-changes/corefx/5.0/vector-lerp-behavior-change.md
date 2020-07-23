---
ms.openlocfilehash: 4bc060f991501b81db0cb7c521e55996a2b5e91e
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281315"
---
### <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a>Изменение в поведении для Vector2.Lerp и Vector4.Lerp

Изменена реализация <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> и <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType>, чтобы корректно учитывать ошибку округления чисел с плавающей запятой.

#### <a name="change-description"></a>Описание изменений

Ранее <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> и <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> были реализованы как `value1 + (value2 - value1) * amount`. Тем не менее, из-за ошибки округления чисел с плавающей запятой этот алгоритм не всегда возвращает `value2`, когда `amount` равно `1.0f`.

В .NET 5.0 и более поздних версий в реализации используется тот же алгоритм, что и в <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, то есть `(value1 * (1.0f - amount)) + (value2 * amount)`. В этом алгоритме корректно учитывается ошибка округления. Таким образом, теперь, если `amount` равно `1.0f`, результат будет точно равен `value2`. Обновленный алгоритм также может быть свободно оптимизирован с использованием <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> (если доступно).

#### <a name="version-introduced"></a>Представленная версия

5.0 (предварительная версия 7)

#### <a name="recommended-action"></a>Рекомендованное действие

Никаких действий не требуется. Если вы хотите сохранить старое поведение, можно реализовать собственную функцию `Lerp`, которая использует предыдущий алгоритм `value1 + (value2 - value1) * amount`.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->
