---
ms.openlocfilehash: 2c44c2e1658f8de556d3f7222de3fa6d4594163a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496337"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a>Десериализация объектов MailMessage, сериализованных в .NET Framework 4.5, может завершиться сбоем

#### <a name="details"></a>Подробнее

Начиная с версии .NET Framework 4.5, объекты <xref:System.Web.Mail.MailMessage> могут содержать символы, отличные от ASCII. В .NET Framework 4 поддерживаются только символы ASCII. В .NET Framework 4 не могут быть десериализованы объекты <xref:System.Web.Mail.MailMessage>, содержащие отличные от ASCII символы и сериализованные в .NET Framework 4.5 или более поздней версии.

#### <a name="suggestion"></a>Предложение

Убедитесь, что в коде реализована обработка исключений при десериализации объекта <xref:System.Web.Mail.MailMessage>.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Web.Mail.MailMessage?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Web.Mail.MailMessage`

-->
