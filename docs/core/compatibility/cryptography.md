---
title: Критические изменения в области шифрования
description: Список критических изменений в области шифрования в .NET Core.
ms.date: 04/22/2020
ms.openlocfilehash: b755876624a7709cfe08b5993655e78be9f8e1f2
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888617"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="e2d48-103">Критические изменения в области шифрования</span><span class="sxs-lookup"><span data-stu-id="e2d48-103">Cryptography breaking changes</span></span>

<span data-ttu-id="e2d48-104">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="e2d48-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="e2d48-105">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="e2d48-105">Breaking change</span></span> | <span data-ttu-id="e2d48-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="e2d48-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="e2d48-107">Изменено значение FeedbackSize по умолчанию для экземпляров, создаваемых методом TripleDES.Create</span><span class="sxs-lookup"><span data-stu-id="e2d48-107">Default FeedbackSize value for instances created by TripleDES.Create changed</span></span>](#default-feedbacksize-value-for-instances-created-by-tripledescreate-changed) | <span data-ttu-id="e2d48-108">5,0</span><span class="sxs-lookup"><span data-stu-id="e2d48-108">5.0</span></span> |
| [<span data-ttu-id="e2d48-109">Создание экземпляров реализаций по умолчанию для криптографических абстракций не поддерживается</span><span class="sxs-lookup"><span data-stu-id="e2d48-109">Instantiating default implementations of cryptographic abstractions is not supported</span></span>](#instantiating-default-implementations-of-cryptographic-abstractions-is-not-supported) | <span data-ttu-id="e2d48-110">5,0</span><span class="sxs-lookup"><span data-stu-id="e2d48-110">5.0</span></span> |
| [<span data-ttu-id="e2d48-111">Комплекты шифров TLS по умолчанию для .NET в Linux</span><span class="sxs-lookup"><span data-stu-id="e2d48-111">Default TLS cipher suites for .NET on Linux</span></span>](#default-tls-cipher-suites-for-net-on-linux) | <span data-ttu-id="e2d48-112">5,0</span><span class="sxs-lookup"><span data-stu-id="e2d48-112">5.0</span></span> |
| [<span data-ttu-id="e2d48-113">Blazor WebAssembly не поддерживает интерфейсы API System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="e2d48-113">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>](#systemsecuritycryptography-apis-not-supported-on-blazor-webassembly) | <span data-ttu-id="e2d48-114">5,0</span><span class="sxs-lookup"><span data-stu-id="e2d48-114">5.0</span></span> |
| [<span data-ttu-id="e2d48-115">Класс System.Security.Cryptography.Oid функционально доступен только для инициализации</span><span class="sxs-lookup"><span data-stu-id="e2d48-115">System.Security.Cryptography.Oid is functionally init-only</span></span>](#systemsecuritycryptographyoid-is-functionally-init-only) | <span data-ttu-id="e2d48-116">5,0</span><span class="sxs-lookup"><span data-stu-id="e2d48-116">5.0</span></span> |
| [<span data-ttu-id="e2d48-117">Синтаксис BEGIN TRUSTED CERTIFICATE больше не поддерживается в Linux</span><span class="sxs-lookup"><span data-stu-id="e2d48-117">BEGIN TRUSTED CERTIFICATE syntax no longer supported on Linux</span></span>](#begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux) | <span data-ttu-id="e2d48-118">3.0</span><span class="sxs-lookup"><span data-stu-id="e2d48-118">3.0</span></span> |
| [<span data-ttu-id="e2d48-119">Для EnvelopedCms по умолчанию используется шифрование AES-256</span><span class="sxs-lookup"><span data-stu-id="e2d48-119">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="e2d48-120">3.0</span><span class="sxs-lookup"><span data-stu-id="e2d48-120">3.0</span></span> |
| [<span data-ttu-id="e2d48-121">Увеличен минимальный размер создаваемых ключей RSAOpenSsl</span><span class="sxs-lookup"><span data-stu-id="e2d48-121">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="e2d48-122">3.0</span><span class="sxs-lookup"><span data-stu-id="e2d48-122">3.0</span></span> |
| [<span data-ttu-id="e2d48-123">Для .NET Core 3.0 более предпочтительным является использование OpenSSL 1.1.x вместо OpenSSL 1.0.x</span><span class="sxs-lookup"><span data-stu-id="e2d48-123">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="e2d48-124">3.0</span><span class="sxs-lookup"><span data-stu-id="e2d48-124">3.0</span></span> |
| [<span data-ttu-id="e2d48-125">CryptoStream.Dispose преобразует окончательный блок только при записи</span><span class="sxs-lookup"><span data-stu-id="e2d48-125">CryptoStream.Dispose transforms final block only when writing</span></span>](#cryptostreamdispose-transforms-final-block-only-when-writing) | <span data-ttu-id="e2d48-126">3.0</span><span class="sxs-lookup"><span data-stu-id="e2d48-126">3.0</span></span> |
| [<span data-ttu-id="e2d48-127">Логический параметр SignedCms.ComputeSignature учитывается</span><span class="sxs-lookup"><span data-stu-id="e2d48-127">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="e2d48-128">2.1</span><span class="sxs-lookup"><span data-stu-id="e2d48-128">2.1</span></span> |

## <a name="net-50"></a><span data-ttu-id="e2d48-129">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="e2d48-129">.NET 5.0</span></span>

[!INCLUDE [tripledes-default-feedback-size-change](../../../includes/core-changes/cryptography/5.0/tripledes-default-feedback-size-change.md)]

***

[!INCLUDE [instantiating-default-implementations-of-cryptographic-abstractions-not-supported](../../../includes/core-changes/cryptography/5.0/instantiating-default-implementations-of-cryptographic-abstractions-not-supported.md)]

<span data-ttu-id="e2d48-130">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e2d48-130">\*\*_</span></span>

[!INCLUDE [default-cipher-suites-for-tls-on-linux](../../../includes/core-changes/cryptography/5.0/default-cipher-suites-for-tls-on-linux.md)]

_*_

[!INCLUDE[Cryptography APIs not supported on Blazor WebAssembly](~/includes/core-changes/cryptography/5.0/cryptography-apis-not-supported-on-blazor-webassembly.md)]

_*_

[!INCLUDE [cryptography-oid-init-only](../../../includes/core-changes/cryptography/5.0/cryptography-oid-init-only.md)]

_*_

## <a name="net-core-30"></a><span data-ttu-id="e2d48-131">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e2d48-131">.NET Core 3.0</span></span>

[!INCLUDE [begin-trusted-cert-linux](~/includes/core-changes/cryptography/3.0/begin-trusted-cert-linux.md)]

_*_

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

_*_

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

_*_

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

_*_

[!INCLUDE [CryptoStream.Dispose transforms final block only when writing](~/includes/core-changes/cryptography/3.0/cryptography-cryptostream-dispose-final-block-write.md)]

_*_

## <a name="net-core-21"></a><span data-ttu-id="e2d48-132">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e2d48-132">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

<span data-ttu-id="e2d48-133">_\*\*</span><span class="sxs-lookup"><span data-stu-id="e2d48-133">_\*\*</span></span>
