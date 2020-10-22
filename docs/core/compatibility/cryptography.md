---
title: Критические изменения в области шифрования
description: Список критических изменений в области шифрования в .NET Core.
ms.date: 04/22/2020
ms.openlocfilehash: 6f37e5caacadc276562e63a728162c6b26f2e435
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159561"
---
# <a name="cryptography-breaking-changes"></a>Критические изменения в области шифрования

На этой странице описаны следующие критические изменения:

| Критическое изменение | Представленная версия |
| - | :-: |
| [Создание экземпляров реализаций по умолчанию для криптографических абстракций не поддерживается](#instantiating-default-implementations-of-cryptographic-abstractions-is-not-supported) | 5,0 |
| [Комплекты шифров TLS по умолчанию для .NET в Linux](#default-tls-cipher-suites-for-net-on-linux) | 5,0 |
| [Blazor WebAssembly не поддерживает интерфейсы API System.Security.Cryptography](#systemsecuritycryptography-apis-not-supported-on-blazor-webassembly) | 5,0 |
| [Класс System.Security.Cryptography.Oid функционально доступен только для инициализации](#systemsecuritycryptographyoid-is-functionally-init-only) | 5,0 |
| [Синтаксис BEGIN TRUSTED CERTIFICATE больше не поддерживается в Linux](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | 3.0 |
| [Для EnvelopedCms по умолчанию используется шифрование AES-256](#envelopedcms-defaults-to-aes-256-encryption) | 3.0 |
| [Увеличен минимальный размер создаваемых ключей RSAOpenSsl](#minimum-size-for-rsaopenssl-key-generation-has-increased) | 3.0 |
| [Для .NET Core 3.0 более предпочтительным является использование OpenSSL 1.1.x вместо OpenSSL 1.0.x](#net-core-30-prefers-openssl-11x-to-openssl-10x) | 3.0 |
| [CryptoStream.Dispose преобразует окончательный блок только при записи](#cryptostreamdispose-transforms-final-block-only-when-writing) | 3.0 |
| [Логический параметр SignedCms.ComputeSignature учитывается](#boolean-parameter-of-signedcmscomputesignature-is-respected) | 2.1 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [instantiating-default-implementations-of-cryptographic-abstractions-not-supported](../../../includes/core-changes/cryptography/5.0/instantiating-default-implementations-of-cryptographic-abstractions-not-supported.md)]

***

[!INCLUDE [default-cipher-suites-for-tls-on-linux](../../../includes/core-changes/cryptography/5.0/default-cipher-suites-for-tls-on-linux.md)]

***

[!INCLUDE[Cryptography APIs not supported on Blazor WebAssembly](~/includes/core-changes/cryptography/5.0/cryptography-apis-not-supported-on-blazor-webassembly.md)]

***

[!INCLUDE [cryptography-oid-init-only](../../../includes/core-changes/cryptography/5.0/cryptography-oid-init-only.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

***

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

[!INCLUDE [CryptoStream.Dispose transforms final block only when writing](~/includes/core-changes/cryptography/3.0/cryptography-cryptostream-dispose-final-block-write.md)]

***

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
