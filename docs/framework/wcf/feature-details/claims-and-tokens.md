---
description: 'Дополнительные сведения: утверждения и токены'
title: Утверждения и маркеры
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], and tokens
ms.assetid: eff167f3-33f8-483d-a950-aa3e9f97a189
ms.openlocfilehash: d7d05fb63886ca7562ce478bcbcea73c3cbafcb8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734962"
---
# <a name="claims-and-tokens"></a>Утверждения и маркеры

В этом разделе описываются различные типы утверждений, которые Windows Communication Foundation (WCF) создают из маркеров по умолчанию, которые он поддерживает.

Анализировать утверждения учетных данных клиента можно с помощью классов <xref:System.IdentityModel.Claims.ClaimSet> и <xref:System.IdentityModel.Claims.Claim>. Класс `ClaimSet` содержит коллекцию объектов `Claim`. Каждый объект `Claim` имеет следующие важные члены.

- Свойство <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> возвращает универсальный код ресурса (URI), который указывает тип делаемого утверждения. Например, тип утверждения может быть отпечаткой сертификата, в этом случае URI имеет значение `http://schemas.microsoft.com/ws/20005/05/identity/claims/thumprint` .

- Свойство <xref:System.IdentityModel.Claims.Claim.Right%2A> возвращает универсальный код ресурса (URI), который указывает право утверждения. Предопределенные права находятся в классе <xref:System.IdentityModel.Claims.Rights> (<xref:System.IdentityModel.Claims.Rights.Identity%2A>, <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>).

- Свойство <xref:System.IdentityModel.Claims.Claim.Resource%2A> возвращает ресурс, связанный с утверждением.

Каждый объект <xref:System.IdentityModel.Claims.ClaimSet> также имеет свойство <xref:System.IdentityModel.Claims.ClaimSet.Issuer%2A>, которое представляет <xref:System.IdentityModel.Claims.ClaimSet> издателя (`Issuer`).

## <a name="windows-accounts"></a>Учетные записи Windows

Когда учетные данные клиента сопоставляются с учетной записью пользователя Windows, полученный в результате объект <xref:System.IdentityModel.Claims.ClaimSet> имеет следующие значения.

- `Issuer` - значение, возвращенное статическим свойством Windows класса <xref:System.IdentityModel.Claims.ClaimSet>.

- Коллекция содержит следующие утверждения.

  - Объект <xref:System.IdentityModel.Claims.Claim>, у которого свойство <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> указывает на идентификатор безопасности (SID), свойство <xref:System.IdentityModel.Claims.Claim.Right%2A> имеет значение `Identity`, а свойство <xref:System.IdentityModel.Claims.Claim.Resource%2A> возвращает фактическое значение идентификатора безопасности. Идентификатор безопасности (SID) - это уникальное значение, выдаваемое контроллером домена каждому пользователю. Идентификатор безопасности используется для идентификации пользователя при взаимодействии с системой безопасности Windows.

  - Объект <xref:System.IdentityModel.Claims.Claim>, у которого свойство <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> указывает на идентификатор безопасности, свойство <xref:System.IdentityModel.Claims.Claim.Right%2A> имеет значение `PossessProperty`, а свойство <xref:System.IdentityModel.Claims.Claim.Resource%2A> представляет собой значение идентификатора безопасности.

  - Объект <xref:System.IdentityModel.Claims.Claim>, у которого свойство <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> имеет значение <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, свойство <xref:System.IdentityModel.Claims.Claim.Right%2A> имеет значение `PossessProperty`, а свойство <xref:System.IdentityModel.Claims.Claim.Resource%2A> представляет собой строку, содержащую имя пользователя (например, "MYMACHINE\Bob").

  - Дополнительные утверждения типа "идентификатор безопасности" со значением <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> для различных групп, к которым принадлежит пользователь.

## <a name="certificates"></a>Сертификаты

Когда учетные данные клиента представляют собой сертификат, полученный в результате объект <xref:System.IdentityModel.Claims.ClaimSet> имеет следующие значения.

- В случае самостоятельно выданного сертификата издателем (`Issuer`) является сам объект <xref:System.IdentityModel.Claims.ClaimSet>. Объект <xref:System.IdentityModel.Claims.ClaimSet> возвращает свойство <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> со значением <xref:System.IdentityModel.Claims.ClaimTypes.Thumbprint%2A>, свойство <xref:System.IdentityModel.Claims.Claim.Right%2A> со значением `Identity` и свойство <xref:System.IdentityModel.Claims.Claim.Resource%2A> со значением, представляющим собой массив типа <xref:System.Byte>, который содержит отпечаток сертификата.

- В случае сертификата, выданного центром сертификации, издателем является `ClaimSet`, представляющий сертификат центра.

- В коллекцию входят следующие утверждения (`Claims`).

  - Объект `Claim`, у которого свойство `ClaimType` указывает на отпечаток, свойство `Right` имеет значение PossessProperty, а значение свойства `Resource` представляет собой байтовый массив, содержащий отпечаток сертификата.

  - Дополнительные утверждения с правом "PossessProperty" различных типов, включая "X500DistinguishedName","Dns", "Name", "Upn" и "Rsa", представляют различные свойства сертификата. Ресурсом для утверждения RSA является открытый ключ, связанный с сертификатом. **Примечание** . Если тип учетных данных клиента — это сертификат, который служба сопоставляет с учетной записью Windows, `ClaimSet` создаются два объекта. Первый объект содержит все утверждения, связанные с учетной записью Windows, а второй содержит все утверждения, связанные с сертификатом.

## <a name="user-namepassword"></a>Имя пользователя/пароль

Когда учетные данные клиента представляют собой имя пользователя/пароль (или эквивалент), которые не сопоставляются с учетной записью Windows, полученный в результате объект `ClaimSet` будет выдан статическим свойством <xref:System.IdentityModel.Claims.ClaimSet.System%2A> класса `ClaimSet`. Объект `ClaimSet` содержит `Identity` утверждение типа <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A> , ресурсом которого является имя пользователя, предоставляемое клиентом. У соответствующего утверждения свойство`Right` имеет значение `PossessProperty`.

## <a name="rsa-keys"></a>Ключи RSA

Если используется ключ RSA, не связанный с сертификатом, полученный результат `ClaimSet` является самозаверяющим и содержит `Identity` утверждение типа <xref:System.IdentityModel.Claims.ClaimTypes.Rsa%2A> , ресурсом которого является ключ RSA. У соответствующего утверждения свойство`Right` имеет значение `PossessProperty`.

## <a name="saml"></a>SAML

Когда для проверки подлинности клиента используется маркер на языке SAML, полученный в результате объект `ClaimSet` будет выдан сущностью, подписавшей маркер SAML; зачастую это сертификат службы маркеров безопасности, которая выдала маркер SAML. Объект `ClaimSet` содержит различные утверждения, обнаруженные в маркере SAML. Если маркер SAML содержит свойство `SamlSubject` с именем, отличным от `null`, создается утверждение с правом `Identity`, типом <xref:System.IdentityModel.Claims.ClaimTypes.NameIdentifier%2A> и ресурсом типа <xref:System.IdentityModel.Tokens.SamlNameIdentifierClaimResource>.

## <a name="identity-claims-and-servicesecuritycontextisanonymous"></a>Идентификационные утверждения и ServiceSecurityContext.IsAnonymous

Если ни один из `ClaimSet` объектов, полученных от учетных данных клиента, не содержит утверждение с параметром, `Right` `Identity,` <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A> свойство возвращает значение `true` . При наличии одного или нескольких таких утверждений свойство `IsAnonymous` возвращает значение `false`.

## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Claims.ClaimSet>
- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.Rights>
- <xref:System.IdentityModel.Claims.ClaimTypes>
- [Управление утверждениями и авторизацией с помощью модели удостоверения](managing-claims-and-authorization-with-the-identity-model.md)
