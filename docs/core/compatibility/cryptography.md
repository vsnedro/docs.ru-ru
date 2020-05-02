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
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="cd2b6-103">Критические изменения в области шифрования</span><span class="sxs-lookup"><span data-stu-id="cd2b6-103">Cryptography breaking changes</span></span>

<span data-ttu-id="cd2b6-104">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="cd2b6-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="cd2b6-105">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="cd2b6-105">Breaking change</span></span> | <span data-ttu-id="cd2b6-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="cd2b6-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="cd2b6-107">Синтаксис BEGIN TRUSTED CERTIFICATE больше не поддерживается в Linux</span><span class="sxs-lookup"><span data-stu-id="cd2b6-107">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="cd2b6-108">3.0</span><span class="sxs-lookup"><span data-stu-id="cd2b6-108">3.0</span></span> |
| [<span data-ttu-id="cd2b6-109">Для EnvelopedCms по умолчанию используется шифрование AES-256</span><span class="sxs-lookup"><span data-stu-id="cd2b6-109">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="cd2b6-110">3.0</span><span class="sxs-lookup"><span data-stu-id="cd2b6-110">3.0</span></span> |
| [<span data-ttu-id="cd2b6-111">Увеличен минимальный размер создаваемых ключей RSAOpenSsl</span><span class="sxs-lookup"><span data-stu-id="cd2b6-111">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="cd2b6-112">3.0</span><span class="sxs-lookup"><span data-stu-id="cd2b6-112">3.0</span></span> |
| [<span data-ttu-id="cd2b6-113">Для .NET Core 3.0 более предпочтительным является использование OpenSSL 1.1.x вместо OpenSSL 1.0.x</span><span class="sxs-lookup"><span data-stu-id="cd2b6-113">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="cd2b6-114">3.0</span><span class="sxs-lookup"><span data-stu-id="cd2b6-114">3.0</span></span> |
| [<span data-ttu-id="cd2b6-115">Улучшенная проверка аргументов в конструкторе Pkcs8PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="cd2b6-115">Better argument validation in the Pkcs8PrivateKeyInfo constructor</span></span>](#better-argument-validation-in-the-pkcs8privatekeyinfo-constructor) | <span data-ttu-id="cd2b6-116">3.0</span><span class="sxs-lookup"><span data-stu-id="cd2b6-116">3.0</span></span> |
| [<span data-ttu-id="cd2b6-117">Логический параметр SignedCms.ComputeSignature учитывается</span><span class="sxs-lookup"><span data-stu-id="cd2b6-117">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="cd2b6-118">2.1</span><span class="sxs-lookup"><span data-stu-id="cd2b6-118">2.1</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="cd2b6-119">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="cd2b6-119">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="cd2b6-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cd2b6-120">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***
