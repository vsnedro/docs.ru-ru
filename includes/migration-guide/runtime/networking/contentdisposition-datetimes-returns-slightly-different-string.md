---
ms.openlocfilehash: c103dff320ae30d02c12ea5c585a47b589da8237
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621421"
---
### <a name="contentdisposition-datetimes-returns-slightly-different-string"></a>ContentDisposition DateTime возвращает немного другую строку

#### <a name="details"></a>Подробнее

Строковые представления <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName> были обновлены, начиная с версии 4.6, чтобы всегда представлять компонент часа <xref:System.DateTime?displayProperty=fullName> с использованием двух цифр. Это сделано в соответствии с [RFC822](https://www.ietf.org/rfc/rfc0822.txt) и [RFC2822](https://www.ietf.org/rfc/rfc2822.txt). В результате <xref:System.Net.Mime.ContentDisposition.ToString> возвращает немного другую строку в 4.6 в сценариях, где один из элементов времени расположения имел значение, предшествующее 10:00. Обратите внимание, что ContentDispositions иногда сериализуются посредством преобразования в строки, поэтому следует проверить все операции <xref:System.Net.Mime.ContentDisposition.ToString>, сериализации или вызовы GetHashCode.

#### <a name="suggestion"></a>Предложение

Не ожидается, что строковые представления ContentDispositions из разных версий .NET Framework будут правильно сравниваться друг с другом. Если возможно, перед сравнением преобразуйте строки обратно в ContentDispositions.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.6|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=nameWithType></li><li><xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=nameWithType></li></ul>|
