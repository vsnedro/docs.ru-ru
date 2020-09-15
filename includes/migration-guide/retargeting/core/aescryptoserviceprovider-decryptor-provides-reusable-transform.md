---
ms.openlocfilehash: 36a9db601f7637185bf48dfcbe2233b4489fcdcf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614657"
---
### <a name="aescryptoserviceprovider-decryptor-provides-a-reusable-transform"></a><span data-ttu-id="ef5ab-101">Дешифратор AesCryptoServiceProvider предоставляет преобразование для повторного использования</span><span class="sxs-lookup"><span data-stu-id="ef5ab-101">AesCryptoServiceProvider decryptor provides a reusable transform</span></span>

#### <a name="details"></a><span data-ttu-id="ef5ab-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ef5ab-102">Details</span></span>

<span data-ttu-id="ef5ab-103">Начиная с приложений, предназначенных для .NET Framework 4.6.2, дешифратор <xref:System.Security.Cryptography.AesCryptoServiceProvider> возвращает преобразование, которое можно использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="ef5ab-103">Starting with apps that target the .NET Framework 4.6.2, the <xref:System.Security.Cryptography.AesCryptoServiceProvider> decryptor provides a reusable transform.</span></span> <span data-ttu-id="ef5ab-104">Это преобразование повторно инициализируется после вызова <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> и его можно использовать снова.</span><span class="sxs-lookup"><span data-stu-id="ef5ab-104">After a call to <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>, the transform is reinitialized and can be reused.</span></span> <span data-ttu-id="ef5ab-105">В приложениях, предназначенных для более ранних версий платформы .NET Framework, попытка повторного использования дешифратора путем вызова <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName> после вызова <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> приводит к исключению <xref:System.Security.Cryptography.CryptographicException> или к повреждению данных.</span><span class="sxs-lookup"><span data-stu-id="ef5ab-105">For apps that target earlier versions of the .NET Framework, attempting to reuse the decryptor by calling <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName> after a call to <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> throws a <xref:System.Security.Cryptography.CryptographicException> or produces corrupted data.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ef5ab-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="ef5ab-106">Suggestion</span></span>

<span data-ttu-id="ef5ab-107">Влияние этого изменения должно быть минимальным, поскольку это ожидаемое поведение. В приложениях, которые зависят от прежнего поведения, можно отказаться от его изменения, добавив следующий параметр конфигурации в раздел `<runtime>` файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="ef5ab-107">The impact of this change should be minimal, since this is the expected behavior.Applications that depend on the previous behavior can opt out of it using it by adding the following configuration setting to the `<runtime>` section of the application's configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/>
</runtime>
```

<span data-ttu-id="ef5ab-108">Кроме того, это поведение можно включить для приложений, предназначенных для предыдущих версий .NET Framework, но работающих под управлением .NET Framework 4.6.2 или более поздних версий. Для этого добавьте в раздел `<runtime>` файла конфигурации приложения следующий параметр:</span><span class="sxs-lookup"><span data-stu-id="ef5ab-108">In addition, applications that target a previous version of the .NET Framework but are running under a version of the .NET Framework starting with .NET Framework 4.6.2 can opt in to it by adding the following configuration setting to the `<runtime>` section of the application's configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/>
</runtime>
```

| <span data-ttu-id="ef5ab-109">name</span><span class="sxs-lookup"><span data-stu-id="ef5ab-109">Name</span></span>    | <span data-ttu-id="ef5ab-110">Значение</span><span class="sxs-lookup"><span data-stu-id="ef5ab-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ef5ab-111">Область</span><span class="sxs-lookup"><span data-stu-id="ef5ab-111">Scope</span></span>   | <span data-ttu-id="ef5ab-112">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="ef5ab-112">Minor</span></span>       |
| <span data-ttu-id="ef5ab-113">Version</span><span class="sxs-lookup"><span data-stu-id="ef5ab-113">Version</span></span> | <span data-ttu-id="ef5ab-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="ef5ab-114">4.6.2</span></span>       |
| <span data-ttu-id="ef5ab-115">Type</span><span class="sxs-lookup"><span data-stu-id="ef5ab-115">Type</span></span>    | <span data-ttu-id="ef5ab-116">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="ef5ab-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="ef5ab-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="ef5ab-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor?displayProperty=nameWithType>
