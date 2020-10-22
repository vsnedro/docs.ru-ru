---
ms.openlocfilehash: d312ba2a22797ff6afff6b893f998c965e68e86e
ms.sourcegitcommit: e078b7540a8293ca1b604c9c0da1ff1506f0170b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "91997750"
---
### <a name="default-tls-cipher-suites-for-net-on-linux"></a><span data-ttu-id="b6068-101">Комплекты шифров TLS по умолчанию для .NET в Linux</span><span class="sxs-lookup"><span data-stu-id="b6068-101">Default TLS cipher suites for .NET on Linux</span></span>

<span data-ttu-id="b6068-102">Теперь .NET для Linux учитывает конфигурацию OpenSSL для наборов шифров по умолчанию при выполнении шифрования TLS/SSL с помощью класса <xref:System.Net.Security.SslStream> или операций более высокого уровня, таких как HTTPS с помощью класса <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="b6068-102">.NET, on Linux, now respects the OpenSSL configuration for default cipher suites when doing TLS/SSL via the <xref:System.Net.Security.SslStream> class or higher-level operations, such as HTTPS via the <xref:System.Net.Http.HttpClient> class.</span></span> <span data-ttu-id="b6068-103">Если комплекты шифров по умолчанию не настроены явно, .NET для Linux использует строго ограниченный список разрешенных комплектов шифров.</span><span class="sxs-lookup"><span data-stu-id="b6068-103">When default cipher suites aren't explicitly configured, .NET on Linux uses a tightly restricted list of permitted cipher suites.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b6068-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="b6068-104">Change description</span></span>

<span data-ttu-id="b6068-105">В предыдущих версиях .NET не учитывается конфигурация системы для комплектов шифров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b6068-105">In previous .NET versions, .NET does not respect system configuration for default cipher suites.</span></span> <span data-ttu-id="b6068-106">Список комплектов шифров по умолчанию для .NET в Linux является нестрогим.</span><span class="sxs-lookup"><span data-stu-id="b6068-106">The default cipher suite list for .NET on Linux is very permissive.</span></span>

<span data-ttu-id="b6068-107">Начиная с .NET 5.0 .NET для Linux учитывает конфигурацию OpenSSL для комплектов шифров по умолчанию, если она указана в файле *openssl.cnf*.</span><span class="sxs-lookup"><span data-stu-id="b6068-107">Starting in .NET 5.0, .NET on Linux respects the OpenSSL configuration for default cipher suites when it's specified in *openssl.cnf*.</span></span> <span data-ttu-id="b6068-108">Если комплекты шифров не настроены явно, единственными разрешенными комплектами шифров являются следующие:</span><span class="sxs-lookup"><span data-stu-id="b6068-108">When cipher suites aren't explicitly configured, the only permitted cipher suites are as follows:</span></span>

- <span data-ttu-id="b6068-109">Комплекты шифров TLS 1.3</span><span class="sxs-lookup"><span data-stu-id="b6068-109">TLS 1.3 cipher suites</span></span>
- <span data-ttu-id="b6068-110">TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384</span><span class="sxs-lookup"><span data-stu-id="b6068-110">TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384</span></span>
- <span data-ttu-id="b6068-111">TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256</span><span class="sxs-lookup"><span data-stu-id="b6068-111">TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256</span></span>
- <span data-ttu-id="b6068-112">TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384</span><span class="sxs-lookup"><span data-stu-id="b6068-112">TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384</span></span>
- <span data-ttu-id="b6068-113">TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256</span><span class="sxs-lookup"><span data-stu-id="b6068-113">TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256</span></span>
- <span data-ttu-id="b6068-114">TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384</span><span class="sxs-lookup"><span data-stu-id="b6068-114">TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384</span></span>
- <span data-ttu-id="b6068-115">TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="b6068-115">TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256</span></span>
- <span data-ttu-id="b6068-116">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384</span><span class="sxs-lookup"><span data-stu-id="b6068-116">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384</span></span>
- <span data-ttu-id="b6068-117">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="b6068-117">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256</span></span>

<span data-ttu-id="b6068-118">Поскольку это резервное значение по умолчанию не включает комплекты шифров, которые совместимы с TLS 1.0 или TLS 1.1, эти старые версии протоколов по умолчанию отключаются.</span><span class="sxs-lookup"><span data-stu-id="b6068-118">Since this fallback default doesn't include any cipher suites that are compatible with TLS 1.0 or TLS 1.1, these older protocol versions are effectively disabled by default.</span></span>

<span data-ttu-id="b6068-119">Если указано значение CipherSuitePolicy для SslStream для конкретного сеанса, по-прежнему будет заменяться содержимое файла конфигурации и (или) резервное значение по умолчанию .NET.</span><span class="sxs-lookup"><span data-stu-id="b6068-119">Supplying a CipherSuitePolicy value to SslStream for a specific session will still replace the configuration file content and/or .NET fallback default.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b6068-120">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="b6068-120">Reason for change</span></span>

<span data-ttu-id="b6068-121">Пользователи, работающие с .NET для Linux, запрашивают изменение конфигурации по умолчанию для <xref:System.Net.Security.SslStream> на ту, которая обеспечивает высокую степень безопасности согласно результатам сторонних средств оценки.</span><span class="sxs-lookup"><span data-stu-id="b6068-121">Users running .NET on Linux requested that the default configuration for <xref:System.Net.Security.SslStream> be changed to one that provided a high security rating from third-party assessment tools.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b6068-122">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="b6068-122">Version introduced</span></span>

<span data-ttu-id="b6068-123">5.0 (RC1)</span><span class="sxs-lookup"><span data-stu-id="b6068-123">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b6068-124">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="b6068-124">Recommended action</span></span>

<span data-ttu-id="b6068-125">Новые значения по умолчанию, скорее всего, будут работать при взаимодействии с современными клиентами или серверами.</span><span class="sxs-lookup"><span data-stu-id="b6068-125">The new defaults are likely to work when communicating with modern clients or servers.</span></span> <span data-ttu-id="b6068-126">Если необходимо расширить список комплектов шифров по умолчанию для работы с устаревшими клиентами (или для взаимодействия с устаревшими серверами), укажите значение `CipherSuitePolicy` или измените файл конфигурации OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="b6068-126">If you need to expand the default cipher suite list to accept legacy clients (or to contact legacy servers), either specify a `CipherSuitePolicy` value or change the OpenSSL configuration file.</span></span> <span data-ttu-id="b6068-127">Во многих дистрибутивах Linux файл конфигурации OpenSSL находится по пути */etc/ssl/openssl.cnf*.</span><span class="sxs-lookup"><span data-stu-id="b6068-127">On many Linux distributions, the OpenSSL configuration file is at */etc/ssl/openssl.cnf*.</span></span>

<span data-ttu-id="b6068-128">В этом примере файл *openssl.cnf* определяет минимальный набор правил, эквивалентный заданной по умолчанию политике комплектов шифров для .NET 5.0 и более поздних версий для Linux.</span><span class="sxs-lookup"><span data-stu-id="b6068-128">This sample *openssl.cnf* file is a minimal file that's equivalent to the default cipher suites policy for .NET 5.0 and later on Linux.</span></span> <span data-ttu-id="b6068-129">Вместо замены системного файла объедините эти понятия с файлом, который присутствует в вашей системе.</span><span class="sxs-lookup"><span data-stu-id="b6068-129">Instead of replacing the system file, merge these concepts with the file that's present on your system.</span></span>

```ini
openssl_conf = default_conf

[default_conf]
ssl_conf = ssl_sect

[ssl_sect]
system_default = system_default_sect

[system_default_sect]
CipherString = ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES256-SHA384:ECDHE-RSA-AES128-SHA256
```

<span data-ttu-id="b6068-130">В дистрибутивах Red Hat Enterprise Linux, CentOS и Fedora в приложениях .NET по умолчанию используются комплекты шифров, разрешенные политиками шифрования на уровне системы.</span><span class="sxs-lookup"><span data-stu-id="b6068-130">On the Red Hat Enterprise Linux, CentOS, and Fedora distributions, .NET applications default to the cipher suites permitted by the system-wide cryptographic policies.</span></span> <span data-ttu-id="b6068-131">В этих дистрибутивах следует использовать конфигурацию политик шифрования вместо *openssl.cnf*.</span><span class="sxs-lookup"><span data-stu-id="b6068-131">On these distributions, use the crypto-policies configuration instead of *openssl.cnf*.</span></span>

#### <a name="category"></a><span data-ttu-id="b6068-132">Категория</span><span class="sxs-lookup"><span data-stu-id="b6068-132">Category</span></span>

- <span data-ttu-id="b6068-133">Шифрование</span><span class="sxs-lookup"><span data-stu-id="b6068-133">Cryptography</span></span>
- <span data-ttu-id="b6068-134">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b6068-134">Security</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b6068-135">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b6068-135">Affected APIs</span></span>

<span data-ttu-id="b6068-136">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="b6068-136">Not detectible via API analysis.</span></span>

<!--

#### Affected APIs

- Not detectible via API analysis.

-->
