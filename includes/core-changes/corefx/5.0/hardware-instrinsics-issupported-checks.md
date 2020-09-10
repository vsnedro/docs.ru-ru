---
ms.openlocfilehash: bba9659b92e5aabc276c585929c99898316036c5
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359143"
---
### <a name="hardware-intrinsic-issupported-checks-may-differ-for-nested-types"></a>Встроенные проверки IsSupported, поддерживаемые оборудованием, могут отличаться для вложенных типов

Проверка `<Isa>.X64.IsSupported`, где `<Isa>` ссылается на классы в пространстве имен <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType>, теперь может привести к другим результатам в предыдущих версиях .NET.

> [!TIP]
> *ISA* означает стандартную промышленную архитектуру.

#### <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 8

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET некоторые встроенные в оборудование типы <xref:System.Runtime.Intrinsics.X86>, например <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType>, не содержали вложенный класс `X64`. Для этих типов вызов `<Isa>.X64.IsSupported` разрешался в свойство `IsSupported` вложенного класса `X64` родительского класса `<Isa>`. Это означало, что свойство может возвращать `true` даже тогда, когда `<Isa>.IsSupported` возвращает `false`.

В .NET 5.0 и более поздних версиях все типы <xref:System.Runtime.Intrinsics.X86> предоставляют вложенный класс `X64`, который поддерживает соответствующие отчеты. Это гарантирует, что общая иерархия останется правильной и что если `<Isa>.X64.IsSupported` `true`, то `<Isa>.IsSupported` также может считаться `true`.

#### <a name="reason-for-change"></a>Причина изменения

Предполагалось, что если `<Isa>.X64.IsSupported` `true`, то `<Isa>.IsSupported` также предполагается `true`. Тем не менее, из-за того, как работает разрешение члена C#, классы, у которых нет вложенного класса `X64`, это было не всегда, что приводило к ошибкам в пользовательском коде.

#### <a name="recommended-action"></a>Рекомендуемое действие

При необходимости настройте код, проверяющий `IsSupported` для поиска соответствующего ISA.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported`

-->
