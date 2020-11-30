---
ms.openlocfilehash: 78678b4b352bb063d1521e9aee3492c0cee059b8
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032135"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a>Исключение InvalidAsynchronousStateException перенесено в другую сборку

Класс <xref:System.ComponentModel.InvalidAsynchronousStateException> перемещен.

#### <a name="change-description"></a>Описание изменений

В .NET Core 2.2 и более ранних версиях класс <xref:System.ComponentModel.InvalidAsynchronousStateException> находится в сборке *System.ComponentModel.TypeConverter*.

Начиная с .NET Core 3.0, он находится в сборке *System.ComponentModel.Primitives*.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендованное действие

Это изменение влияет только на приложения, использующие отражение для загрузки <xref:System.ComponentModel.InvalidAsynchronousStateException> путем вызова метода, такого как <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>, или перегрузки <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>, которая предполагает, что тип находится в определенной сборке. В этом случае обновите сборку, указанную в вызове метода, в соответствии с новым расположением сборки типа.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

Отсутствует.

<!--

#### Affected APIs

- Not detectable via API analysis

-->
