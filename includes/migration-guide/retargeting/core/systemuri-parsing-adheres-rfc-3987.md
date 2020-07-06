---
ms.openlocfilehash: 9c3c0bf7fbd8d45eba84eaa8634fd2d834195702
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617277"
---
### <a name="systemuri-parsing-adheres-to-rfc-3987"></a>Синтаксический анализ System.Uri соответствует стандарту RFC 3987

#### <a name="details"></a>Подробнее

Синтаксический анализ URI претерпел ряд изменений в .NET Framework 4.5. Обратите внимание, что эти изменения касаются только кода, предназначенного для .NET Framework 4.5. Если двоичный файл предназначен для .NET Framework 4.0, будет действовать старое поведение. В синтаксический анализ URI в .NET Framework 4.5 внесены следующие изменения:

- Синтаксический анализ URI будет выполнять проверку нормализации и символов в соответствии с последними правилами IRI стандарта RFC 3987.
- Форма нормализации Юникода C будет выполняться только в части узла URI.
- Недопустимые URI mailto: теперь будут вызывать исключение.
- Конечные точки в конце сегмента пути теперь сохраняются.
- Идентификаторы URI `file://` не экранируют символ `?`.
- Управляющие символы Юникода с `U+0080` по `U+009F` не поддерживаются.
- Символы запятой `,` или `%2c` не отменяются автоматически.

#### <a name="suggestion"></a>Предложение

Если необходимы старые семантики синтаксического анализа URI в .NET Framework 4.0 (часто они не требуются), их можно использовать, нацелив приложение на .NET Framework 4.0. Это можно сделать с помощью <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> в сборке или в пользовательском интерфейсе системы проектов Visual Studio на странице свойств проекта.

| name    | Значение       |
|:--------|:------------|
| Область   | Значительно       |
| Version | 4.5         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Uri.%23ctor(System.String)>
- <xref:System.Uri.%23ctor(System.String,System.Boolean)>
- <xref:System.Uri.%23ctor(System.String,System.UriKind)>
- <xref:System.Uri.%23ctor(System.Uri,System.String)>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
