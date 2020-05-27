---
ms.openlocfilehash: 3c6142fd536bad5676f02570fecd4eb0605db829
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721598"
---
### <a name="begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux"></a><span data-ttu-id="ecd76-101">Синтаксис "BEGIN TRUSTED CERTIFICATE" больше не поддерживается для корневых сертификатов в Linux</span><span class="sxs-lookup"><span data-stu-id="ecd76-101">"BEGIN TRUSTED CERTIFICATE" syntax no longer supported for root certificates on Linux</span></span>

<span data-ttu-id="ecd76-102">Корневые сертификаты в Linux и других Unix-подобных системах (но не macOS) можно представить в двух формах: стандартный заголовок PEM `BEGIN CERTIFICATE` и относящийся к OpenSSL заголовок PEM `BEGIN TRUSTED CERTIFICATE`.</span><span class="sxs-lookup"><span data-stu-id="ecd76-102">Root certificates on Linux and other Unix-like systems (but not macOS) can be presented in two forms: the standard `BEGIN CERTIFICATE` PEM header, and the OpenSSL-specific `BEGIN TRUSTED CERTIFICATE` PEM header.</span></span> <span data-ttu-id="ecd76-103">Последний синтаксис допускает дополнительную конфигурацию, которая вызвала проблемы совместимости с классом <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName> .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ecd76-103">The latter syntax allows for additional configuration that has caused compatibility issues with .NET Core's <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName> class.</span></span> <span data-ttu-id="ecd76-104">Содержимое корневого сертификата `BEGIN TRUSTED CERTIFICATE` больше не загружается подсистемой цепочек, начиная с .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="ecd76-104">`BEGIN TRUSTED CERTIFICATE` root certificate contents are no longer loaded by the chain engine starting in .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ecd76-105">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="ecd76-105">Change description</span></span>

<span data-ttu-id="ecd76-106">Ранее синтаксисы `BEGIN CERTIFICATE` и `BEGIN TRUSTED CERTIFICATE` использовались для заполнения списка корневого доверия.</span><span class="sxs-lookup"><span data-stu-id="ecd76-106">Previously, both the `BEGIN CERTIFICATE` and `BEGIN TRUSTED CERTIFICATE` syntaxes were used to populate the root trust list.</span></span> <span data-ttu-id="ecd76-107">Если использовался синтаксис `BEGIN TRUSTED CERTIFICATE` и в файле были указаны дополнительные параметры, <xref:System.Security.Cryptography.X509Certificates.X509Chain> мог сообщить о том, что доверие цепочки было явно запрещено (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="ecd76-107">If the `BEGIN TRUSTED CERTIFICATE` syntax was used and additional options were specified in the file, <xref:System.Security.Cryptography.X509Certificates.X509Chain> may have reported that the chain trust was explicitly disallowed (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType>).</span></span> <span data-ttu-id="ecd76-108">Однако если сертификат был также указан с использованием синтаксиса `BEGIN CERTIFICATE` в ранее загруженном файле, доверие цепочки было разрешено.</span><span class="sxs-lookup"><span data-stu-id="ecd76-108">However, if the certificate was also specified with the `BEGIN CERTIFICATE` syntax in a previously loaded file, the chain trust was allowed.</span></span>

<span data-ttu-id="ecd76-109">Начиная с .NET Core 3.0 содержимое `BEGIN TRUSTED CERTIFICATE` больше не считывается.</span><span class="sxs-lookup"><span data-stu-id="ecd76-109">Starting in .NET Core 3.0, `BEGIN TRUSTED CERTIFICATE` contents are no longer read.</span></span> <span data-ttu-id="ecd76-110">Если сертификат также не указан с использованием стандартного синтаксиса `BEGIN CERTIFICATE`, <xref:System.Security.Cryptography.X509Certificates.X509Chain> сообщает о том, что корень не является доверенным (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="ecd76-110">If the certificate is not also specified via a standard `BEGIN CERTIFICATE` syntax, the <xref:System.Security.Cryptography.X509Certificates.X509Chain> reports that the root is not trusted (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType>).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ecd76-111">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="ecd76-111">Version introduced</span></span>

<span data-ttu-id="ecd76-112">3.0</span><span class="sxs-lookup"><span data-stu-id="ecd76-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ecd76-113">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="ecd76-113">Recommended action</span></span>

<span data-ttu-id="ecd76-114">Это изменение не затрагивает большинство приложений, но приложения, которые не могут видеть оба источника корневых сертификатов из-за проблем с разрешениями, могут столкнуться с непредвиденными ошибками `UntrustedRoot` после обновления.</span><span class="sxs-lookup"><span data-stu-id="ecd76-114">Most applications are unaffected by this change, but applications that cannot see both root certificate sources because of permissions problems may experience unexpected `UntrustedRoot` errors after upgrading.</span></span>

<span data-ttu-id="ecd76-115">Многие дистрибутивы Linux записывают корневые сертификаты в два расположения: каталог с одним сертификатом на файл и объединение в один файл.</span><span class="sxs-lookup"><span data-stu-id="ecd76-115">Many Linux distributions (or distros) write root certificates into two locations: a one-certificate-per-file directory, and a one-file concatenation.</span></span> <span data-ttu-id="ecd76-116">В некоторых дистрибутивах каталог с одним сертификатом на файл использует синтаксис `BEGIN TRUSTED CERTIFICATE`, а объединение в файл использует стандартный синтаксис `BEGIN CERTIFICATE`.</span><span class="sxs-lookup"><span data-stu-id="ecd76-116">On some distros, the one-certificate-per-file directory uses the `BEGIN TRUSTED CERTIFICATE` syntax while the file concatenation uses the standard `BEGIN CERTIFICATE` syntax.</span></span> <span data-ttu-id="ecd76-117">Убедитесь, что все пользовательские корневые сертификаты добавляются как `BEGIN CERTIFICATE` по меньшей мере в одно из этих расположений, а сами эти расположения могут быть считаны приложением.</span><span class="sxs-lookup"><span data-stu-id="ecd76-117">Ensure that any custom root certificates are added as `BEGIN CERTIFICATE` in at least one of these locations, and that both locations can be read by your application.</span></span>

<span data-ttu-id="ecd76-118">Типичным каталогом является */etc/ssl/certs/* , а типичным объединенным файлом — */etc/ssl/cert.pem*.</span><span class="sxs-lookup"><span data-stu-id="ecd76-118">The typical directory is */etc/ssl/certs/* and the typical concatenated file is */etc/ssl/cert.pem*.</span></span> <span data-ttu-id="ecd76-119">Используйте команду `openssl version -d`, чтобы определить корневой каталог, зависящий от платформы, который может отличаться от */etc/ssl/* .</span><span class="sxs-lookup"><span data-stu-id="ecd76-119">Use the command `openssl version -d` to determine the platform-specific root, which may differ from */etc/ssl/*.</span></span> <span data-ttu-id="ecd76-120">Например, в Ubuntu 18.04 этим каталогом является */usr/lib/ssl/certs/* , а этим файлом — */usr/lib/ssl/cert.pem*.</span><span class="sxs-lookup"><span data-stu-id="ecd76-120">For example, on Ubuntu 18.04, the directory is */usr/lib/ssl/certs/* and the file is */usr/lib/ssl/cert.pem*.</span></span> <span data-ttu-id="ecd76-121">Однако */usr/lib/ssl/certs/* является символьной ссылкой на */etc/ssl/certs/* , и */usr/lib/ssl/cert.pem* не существует.</span><span class="sxs-lookup"><span data-stu-id="ecd76-121">However, */usr/lib/ssl/certs/* is a symlink to */etc/ssl/certs/* and */usr/lib/ssl/cert.pem* does not exist.</span></span>

```bash
$ openssl version -d
OPENSSLDIR: "/usr/lib/ssl"
$ ls -al /usr/lib/ssl
total 12
drwxr-xr-x  3 root root 4096 Dec 12 17:10 .
drwxr-xr-x 73 root root 4096 Feb 20 15:18 ..
lrwxrwxrwx  1 root root   14 Mar 27  2018 certs -> /etc/ssl/certs
drwxr-xr-x  2 root root 4096 Dec 12 17:10 misc
lrwxrwxrwx  1 root root   20 Nov 12 16:58 openssl.cnf -> /etc/ssl/openssl.cnf
lrwxrwxrwx  1 root root   16 Mar 27  2018 private -> /etc/ssl/private
```

#### <a name="category"></a><span data-ttu-id="ecd76-122">Категория</span><span class="sxs-lookup"><span data-stu-id="ecd76-122">Category</span></span>

<span data-ttu-id="ecd76-123">Шифрование</span><span class="sxs-lookup"><span data-stu-id="ecd76-123">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ecd76-124">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="ecd76-124">Affected APIs</span></span>

- <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.X509Certificates.X509Chain`

-->
