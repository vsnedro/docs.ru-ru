---
ms.openlocfilehash: 1d9a5bbea49730ee6cf99eaae6b20a0035e70b97
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135608"
---
### <a name="begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux"></a>Синтаксис "BEGIN TRUSTED CERTIFICATE" больше не поддерживается для корневых сертификатов в Linux

Корневые сертификаты в Linux и других Unix-подобных системах (но не macOS) можно представить в двух формах: стандартный заголовок PEM `BEGIN CERTIFICATE` и относящийся к OpenSSL заголовок PEM `BEGIN TRUSTED CERTIFICATE`. Последний синтаксис допускает дополнительную конфигурацию, которая вызвала проблемы совместимости с классом <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName> .NET Core. Содержимое корневого сертификата `BEGIN TRUSTED CERTIFICATE` больше не загружается подсистемой цепочек, начиная с .NET Core 3.0.

#### <a name="change-description"></a>Описание изменений

Ранее синтаксисы `BEGIN CERTIFICATE` и `BEGIN TRUSTED CERTIFICATE` использовались для заполнения списка корневого доверия. Если использовался синтаксис `BEGIN TRUSTED CERTIFICATE` и в файле были указаны дополнительные параметры, <xref:System.Security.Cryptography.X509Certificates.X509Chain> мог сообщить о том, что доверие цепочки было явно запрещено (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType>). Однако если сертификат был также указан с использованием синтаксиса `BEGIN CERTIFICATE` в ранее загруженном файле, доверие цепочки было разрешено.

Начиная с .NET Core 3.0 содержимое `BEGIN TRUSTED CERTIFICATE` больше не считывается. Если сертификат также не указан с использованием стандартного синтаксиса `BEGIN CERTIFICATE`, <xref:System.Security.Cryptography.X509Certificates.X509Chain> сообщает о том, что корень не является доверенным (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType>).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендованное действие

Это изменение не затрагивает большинство приложений, но приложения, которые не могут видеть оба источника корневых сертификатов из-за проблем с разрешениями, могут столкнуться с непредвиденными ошибками `UntrustedRoot` после обновления.

Многие дистрибутивы Linux записывают корневые сертификаты в два расположения: каталог с одним сертификатом на файл и объединение в один файл. В некоторых дистрибутивах каталог с одним сертификатом на файл использует синтаксис `BEGIN TRUSTED CERTIFICATE`, а объединение в файл использует стандартный синтаксис `BEGIN CERTIFICATE`. Убедитесь, что все пользовательские корневые сертификаты добавляются как `BEGIN CERTIFICATE` по меньшей мере в одно из этих расположений, а сами эти расположения могут быть считаны приложением.

Типичным каталогом является */etc/ssl/certs/* , а типичным объединенным файлом — */etc/ssl/cert.pem*. Используйте команду `openssl version -d`, чтобы определить корневой каталог, зависящий от платформы, который может отличаться от */etc/ssl/* . Например, в Ubuntu 18.04 этим каталогом является */usr/lib/ssl/certs/* , а этим файлом — */usr/lib/ssl/cert.pem*. Однако */usr/lib/ssl/certs/* является символьной ссылкой на */etc/ssl/certs/* , и */usr/lib/ssl/cert.pem* не существует.

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

### <a name="category"></a>Категория

Шифрование

### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Security.Cryptography.X509Certificates.X509Chain`

-->
