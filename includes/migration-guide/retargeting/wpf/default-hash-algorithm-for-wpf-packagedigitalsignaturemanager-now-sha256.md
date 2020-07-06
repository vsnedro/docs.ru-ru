---
ms.openlocfilehash: d3e0a61601f60a389b662f6f74934b6e6dc6e663
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614916"
---
### <a name="the-default-hash-algorithm-for-wpf-packagedigitalsignaturemanager-is-now-sha256"></a>В качестве хэш-алгоритма по умолчанию для PackageDigitalSignatureManager WPF теперь используется SHA256

#### <a name="details"></a>Подробнее

`System.IO.Packaging.PackageDigitalSignatureManager` реализует функции цифровой подписи для пакетов WPF.  В .NET Framework 4.7 и более ранних версиях для подписывания частей пакетов по умолчанию использовался хэш-алгоритм SHA1 (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>).  С учетом выявленных проблем с безопасностью SHA1, начиная с версии .NET Framework 4.7.1, теперь по умолчанию используется алгоритм SHA256.  Это изменение затрагивает все операции подписывания пакетов, включая документы XPS.

#### <a name="suggestion"></a>Предложение

Тем разработчикам, которые хотят реализовать это изменение в приложениях для версий платформы .NET Framework ниже 4.7.1, а также тем, кому необходимо использовать старые функции в приложениях для версии .NET Framework 4.7.1 или более поздних, необходимо соответствующим образом установить флаг AppContext.  Чтобы использовать алгоритм SHA1, следует установить значение true. Значение false позволяет использовать алгоритм SHA256.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.UseSha1AsDefaultHashAlgorithmForDigitalSignatures=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.7.1       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>
