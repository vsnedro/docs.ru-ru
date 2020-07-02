---
ms.openlocfilehash: 0f87f9e9b87860da97ce96e18104b44ec4327c91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621228"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a>WCF PipeConnection.GetHashAlgorithm теперь использует SHA256

#### <a name="details"></a>Подробнее

Начиная с версии .NET Framework 4.7.1 Windows Communication Foundation использует хэш SHA256 для формирования случайных имен для именованных каналов. В .NET Framework 4.7 и более ранних версиях используется хэш SHA-1.

#### <a name="suggestion"></a>Предложение

Если из-за этого изменения в .NET Framework 4.7.1 или более поздних версий вы сталкиваетесь с проблемами совместимости, вы можете отключить это изменение, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Версия|4.7.1|
|Type|Среда выполнения|
