---
ms.openlocfilehash: 0b62eff8d70873293aafa539f40bf032672df57a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616291"
---
### <a name="managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode"></a><span data-ttu-id="44ff9-101">Управляемые криптографические классы, которые не вызывают исключение CryptographyException в режиме FIPS</span><span class="sxs-lookup"><span data-stu-id="44ff9-101">Managed cryptography classes do not throw a CryptographyException in FIPS mode</span></span>

#### <a name="details"></a><span data-ttu-id="44ff9-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="44ff9-102">Details</span></span>

<span data-ttu-id="44ff9-103">В .NET Framework 4.7.2 и более ранних версий управляемые классы поставщиков служб шифрования, такие как <xref:System.Security.Cryptography.SHA256Managed>, выдавали исключение <xref:System.Security.Cryptography.CryptographicException> во время настройки системных библиотек шифрования в режиме FIPS.</span><span class="sxs-lookup"><span data-stu-id="44ff9-103">In .NET Framework 4.7.2 and earlier versions, managed cryptographic provider classes such as <xref:System.Security.Cryptography.SHA256Managed> throw a <xref:System.Security.Cryptography.CryptographicException> when the system cryptographic libraries are configured in FIPS mode.</span></span> <span data-ttu-id="44ff9-104">Эти исключения создаются, так как управляемые версии не прошли сертификацию FIPS 140-2, а также для запрета алгоритмов шифрования, которые не одобрены правилами FIPS.</span><span class="sxs-lookup"><span data-stu-id="44ff9-104">These exceptions are thrown because the managed versions have not undergone FIPS (Federal Information Processing Standards) 140-2 certification, as well as to block cryptographic algorithms that were not considered to be approved based on the FIPS rules.</span></span>  <span data-ttu-id="44ff9-105">Так как у некоторых разработчиков компьютеры разработки работают в режиме FIPS, эти исключения часто вызываются только в рабочих системах. Приложения, предназначенные для .NET Framework 4.8 и более поздних версий, автоматически переключаются на более новую и нестрогую политику, чтобы исключение <xref:System.Security.Cryptography.CryptographicException> больше не вызывалось по умолчанию в таких случаях.</span><span class="sxs-lookup"><span data-stu-id="44ff9-105">Because few developers have their development machines in FIPS mode, these exceptions are frequently thrown only on production systems.Applications that target .NET Framework 4.8 and later versions automatically switch to the newer, relaxed policy, so that a <xref:System.Security.Cryptography.CryptographicException> is no longer thrown by default in such cases.</span></span> <span data-ttu-id="44ff9-106">Вместо этого управляемые классы шифрования перенацеливают криптографические операции на системную библиотеку шифрования.</span><span class="sxs-lookup"><span data-stu-id="44ff9-106">Instead, the managed cryptography classes redirect cryptographic operations to a system cryptography library.</span></span> <span data-ttu-id="44ff9-107">Это изменение политики эффективно устраняет возможное заблуждение относительно различий между средами разработки и рабочими средами, применяя к собственным и управляемым компонентам одну и ту же политику шифрования.</span><span class="sxs-lookup"><span data-stu-id="44ff9-107">This policy change effectively removes a potentially confusing difference between developer environments and the production environments and makes native components and managed components operate under the same cryptographic policy.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="44ff9-108">Предложение</span><span class="sxs-lookup"><span data-stu-id="44ff9-108">Suggestion</span></span>

<span data-ttu-id="44ff9-109">Если такое поведение нежелательно, вы можете отказаться от него и восстановить предыдущее поведение, чтобы исключение <xref:System.Security.Cryptography.CryptographicException> вызывалось в режиме FIPS, добавив следующий параметр конфигурации [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="44ff9-109">If this behavior is undesirable, you can opt out of it and restore the previous behavior so that a <xref:System.Security.Cryptography.CryptographicException> is thrown in FIPS mode by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=true" />
</runtime>
```

<span data-ttu-id="44ff9-110">Если приложение предназначено для .NET Framework 4.7.2 или более ранних версий, можно также включить это изменение, добавив следующий параметр конфигурации [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в раздел [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="44ff9-110">If your application targets .NET Framework 4.7.2 or earlier, you can also opt in to this change by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=false" />
</runtime>
```

| <span data-ttu-id="44ff9-111">name</span><span class="sxs-lookup"><span data-stu-id="44ff9-111">Name</span></span>    | <span data-ttu-id="44ff9-112">Значение</span><span class="sxs-lookup"><span data-stu-id="44ff9-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="44ff9-113">Область</span><span class="sxs-lookup"><span data-stu-id="44ff9-113">Scope</span></span>   | <span data-ttu-id="44ff9-114">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="44ff9-114">Edge</span></span>        |
| <span data-ttu-id="44ff9-115">Version</span><span class="sxs-lookup"><span data-stu-id="44ff9-115">Version</span></span> | <span data-ttu-id="44ff9-116">4.8</span><span class="sxs-lookup"><span data-stu-id="44ff9-116">4.8</span></span>         |
| <span data-ttu-id="44ff9-117">Type</span><span class="sxs-lookup"><span data-stu-id="44ff9-117">Type</span></span>    | <span data-ttu-id="44ff9-118">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="44ff9-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="44ff9-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="44ff9-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5Cng?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RijndaelManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RIPEMD160Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA1Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA256Managed?displayProperty=nameWithType>
