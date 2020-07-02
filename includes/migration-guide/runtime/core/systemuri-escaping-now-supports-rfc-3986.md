---
ms.openlocfilehash: 1d7dc808d5b514acc582675d6ccdbd5778314624
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620589"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a>Экранирование System.Uri теперь поддерживает RFC 3986

#### <a name="details"></a>Подробнее

Экранирование URI изменилось в .NET Framework 4.5 для поддержки [RFC 3986](https://tools.ietf.org/html/rfc3986). Внесены следующие конкретные изменения.<ul><li>Метод <xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> преобразует в escape-последовательность зарезервированные символы в соответствии с RFC 3986.</li><li>Метод <xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> не преобразует в escape-последовательность зарезервированные символы.</li><li>Метод <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> не создает исключение, если ему встречается неверная escape-последовательность.</li><li>Преобразование незарезервированных символов в escape-символы отменяется.</li></ul>

#### <a name="suggestion"></a>Предложение

<ul><li>Обновления приложений не зависят от <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> для создания исключения в случае недопустимой escape-последовательности. Такие последовательности должны обнаруживаться сразу же.</li><li>Аналогичным образом ожидается, что экранированные и неэкранированные URI и строки данных могут отличаться в .NET Framework 4.0 и .NET Framework 4.5 и их не следует сравнивать в версиях .NET напрямую. Их необходимо проанализировать и нормализовать в одной версии .NET перед выполнением каких-либо сравнений.</li></ul>

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType></li></ul>|
