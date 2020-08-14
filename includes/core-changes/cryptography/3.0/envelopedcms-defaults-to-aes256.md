---
ms.openlocfilehash: e0cdcce9b8c7d591925b08635e3354dadaf22b7b
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556035"
---
### <a name="envelopedcms-defaults-to-aes-256-encryption"></a><span data-ttu-id="d9d8a-101">Для EnvelopedCms по умолчанию используется шифрование AES-256</span><span class="sxs-lookup"><span data-stu-id="d9d8a-101">EnvelopedCms defaults to AES-256 encryption</span></span>

<span data-ttu-id="d9d8a-102">Алгоритм симметричного шифрования по умолчанию, используемый `EnvelopedCms`, изменен с TripleDES на AES-256.</span><span class="sxs-lookup"><span data-stu-id="d9d8a-102">The default symmetric encryption algorithm used by `EnvelopedCms` has changed from TripleDES to AES-256.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d9d8a-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="d9d8a-103">Change description</span></span>

<span data-ttu-id="d9d8a-104">В прошлых версиях при использовании <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> для шифрования данных без указания алгоритма симметричного шифрования с помощью перегрузки конструктора данные зашифровываются с помощью алгоритма TripleDES/3DES/3DEA/DES3-EDE.</span><span class="sxs-lookup"><span data-stu-id="d9d8a-104">In previous versions, when <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> is used to encrypt data without specifying a symmetric encryption algorithm via a constructor overload, the data is encrypted with the TripleDES/3DES/3DEA/DES3-EDE algorithm.</span></span>

<span data-ttu-id="d9d8a-105">Начиная с .NET Core 3.0 (устанавливается с помощью пакета NuGet [System.Security.Cryptography.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/) версии 4.6.0) алгоритм по умолчанию был заменен на AES-256 с целью модернизации и повышения безопасности стандартных параметров.</span><span class="sxs-lookup"><span data-stu-id="d9d8a-105">Starting with .NET Core 3.0 (via version 4.6.0 of the [System.Security.Cryptography.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/) NuGet package), the default algorithm has been changed to AES-256 for algorithm modernization and to improve the security of default options.</span></span> <span data-ttu-id="d9d8a-106">Если в сертификате получателя сообщения используется открытый ключ Диффи-Хеллмана (не EC) операция шифрования может завершиться ошибкой <xref:System.Security.Cryptography.CryptographicException> из-за ограничений базовой платформы.</span><span class="sxs-lookup"><span data-stu-id="d9d8a-106">If a message recipient certificate has a (non-EC) Diffie-Hellman public key, the encryption operation may fail with a <xref:System.Security.Cryptography.CryptographicException> due to limitations in the underlying platform.</span></span>

<span data-ttu-id="d9d8a-107">В приведенном ниже примере кода показано, что в .NET Core 2.2 и более ранних версиях для шифрования данных используется TripleDES.</span><span class="sxs-lookup"><span data-stu-id="d9d8a-107">In the following sample code, the data is encrypted with TripleDES if running on .NET Core 2.2 or earlier.</span></span> <span data-ttu-id="d9d8a-108">При работе в .NET Core 3.0 и более поздних версиях для шифрования используется AES-256.</span><span class="sxs-lookup"><span data-stu-id="d9d8a-108">If running on .NET Core 3.0 or later, it's encrypted with AES-256.</span></span>

```csharp
EnvelopedCms cms = new EnvelopedCms(content);
cms.Encrypt(recipient);
return cms.Encode();
```

#### <a name="version-introduced"></a><span data-ttu-id="d9d8a-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="d9d8a-109">Version introduced</span></span>

<span data-ttu-id="d9d8a-110">3.0</span><span class="sxs-lookup"><span data-stu-id="d9d8a-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d9d8a-111">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="d9d8a-111">Recommended action</span></span>

<span data-ttu-id="d9d8a-112">Если изменение отрицательно повлияет на работу, можете восстановить шифрование TripleDES, явно указав идентификатор алгоритма шифрования в конструкторе <xref:System.Security.Cryptography.Pkcs.EnvelopedCms>, который содержит параметр типа <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier>, например:</span><span class="sxs-lookup"><span data-stu-id="d9d8a-112">If you are negatively impacted by the change, you can restore TripleDES encryption by explicitly specifying the encryption algorithm identifier in an <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> constructor that includes a parameter of type <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier>, such as:</span></span>

```csharp
Oid tripleDesOid = new Oid("1.2.840.113549.3.7", null);
AlgorithmIdentifier tripleDesIdentifier = new AlgorithmIdentifier(tripleDesOid);
EnvelopedCms cms = new EnvelopedCms(content, tripleDesIdentifier);

cms.Encrypt(recipient);
return cms.Encode()l
```

#### <a name="category"></a><span data-ttu-id="d9d8a-113">Категория</span><span class="sxs-lookup"><span data-stu-id="d9d8a-113">Category</span></span>

<span data-ttu-id="d9d8a-114">Шифрование</span><span class="sxs-lookup"><span data-stu-id="d9d8a-114">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d9d8a-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d9d8a-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.ContentInfo)>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor(System.Security.Cryptography.Pkcs.ContentInfo)`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)`

-->
