---
ms.openlocfilehash: cf51d5f6b3eee7189fd9613b3d780a829d197a04
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558012"
---
### <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a>Класс System.Security.Cryptography.Oid функционально доступен только для инициализации

Класс <xref:System.Security.Cryptography.Oid?displayProperty=fullName>, используемый для представления значений идентификаторов объектов ASN.1 и их понятных имен, был ранее полностью изменяемым. Эта изменяемость часто игнорировалась или становилась неожиданностью. Теперь методы задания свойств вызывают <xref:System.PlatformNotSupportedException> при попытке изменить значение после того, как оно уже было назначено.

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях методы задания свойств в <xref:System.Security.Cryptography.Oid> можно было использовать для изменения значений свойств <xref:System.Security.Cryptography.Oid.FriendlyName> и <xref:System.Security.Cryptography.Oid.Value>.

В .NET 5.0 и более поздних версиях методы задания свойств можно использовать только для инициализации значения. После того как свойство получило значение из конструктора или предыдущего вызова метода задания свойств, метод задания свойств всегда будет вызывать <xref:System.PlatformNotSupportedException>.

#### <a name="reason-for-change"></a>Причина изменения

Это изменение позволяет повторно использовать объекты <xref:System.Security.Cryptography.Oid> как часть возвращаемых значений в общедоступных API для уменьшения количества профилей выделения объектов. Это позволяет избежать необходимости создавать временные "защитные" копии, когда значения <xref:System.Security.Cryptography.Oid> используются в качестве входных данных.

#### <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 8

#### <a name="recommended-action"></a>Рекомендованное действие

Избегайте использования методов задания свойств <xref:System.Security.Cryptography.Oid>, отличных от инициализации объектов. Чтобы представить новое значение, используйте новый экземпляр вместо изменения значения существующего объекта.

#### <a name="category"></a>Категория

Шифрование

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

-->
