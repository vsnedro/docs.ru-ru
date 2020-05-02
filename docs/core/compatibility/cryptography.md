---
title: Критические изменения в области шифрования
description: Список критических изменений в области шифрования в .NET Core.
ms.date: 04/22/2020
ms.openlocfilehash: 66049473083d87b4c84408f35a04193a4563c2b3
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135609"
---
# <a name="cryptography-breaking-changes"></a>Критические изменения в области шифрования

На этой странице описаны следующие критические изменения:

| Критическое изменение | Представленная версия |
| - | :-: |
| [Синтаксис BEGIN TRUSTED CERTIFICATE больше не поддерживается в Linux](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | 3.0 |
| [Для EnvelopedCms по умолчанию используется шифрование AES-256](#envelopedcms-defaults-to-aes-256-encryption) | 3.0 |
| [Увеличен минимальный размер создаваемых ключей RSAOpenSsl](#minimum-size-for-rsaopenssl-key-generation-has-increased) | 3.0 |
| [Для .NET Core 3.0 более предпочтительным является использование OpenSSL 1.1.x вместо OpenSSL 1.0.x](#net-core-30-prefers-openssl-11x-to-openssl-10x) | 3.0 |
| [Улучшенная проверка аргументов в конструкторе Pkcs8PrivateKeyInfo](#better-argument-validation-in-the-pkcs8privatekeyinfo-constructor) | 3.0 |
| [Логический параметр SignedCms.ComputeSignature учитывается](#boolean-parameter-of-signedcmscomputesignature-is-respected) | 2.1 |

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

***

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/3.0/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]

***

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
