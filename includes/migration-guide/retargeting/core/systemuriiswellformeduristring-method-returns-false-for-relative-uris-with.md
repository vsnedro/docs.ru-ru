---
ms.openlocfilehash: f7dcf9c4c3dc7ea536ddc847769a1a30f1298bb2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617283"
---
### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a>Метод System.Uri.IsWellFormedUriString возвращает значение false для относительных URI с символом двоеточия в первом сегменте

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.5 <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> будет рассматривать относительные URI с `:` в первом сегменте как некорректные. Это отличается от поведения <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> в .NET Framework 4.0. Изменение было внесено, чтобы обеспечить соответствие RFC3986.

#### <a name="suggestion"></a>Предложение

Это изменение (как и другие изменения URI) повлияет только на приложения, предназначенные для .NET Framework 4.5 (или более поздней версии). Чтобы сохранить старое поведение, необходимо нацелить приложение на .NET Framework 4.0. Кроме того, проверьте URI до вызова метода <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName>, ищущего символы `:`, которые можно удалить в целях проверки, если вы предпочитаете старое поведение.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.5         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType>
