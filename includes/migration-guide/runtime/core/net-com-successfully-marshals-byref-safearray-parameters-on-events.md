---
ms.openlocfilehash: 77e9d28d79a92cf1523e4ef5779d78394b00ae80
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622085"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>.NET COM успешно маршалирует параметры ByRef SafeArray в события

#### <a name="details"></a>Подробнее

В .NET Framework 4.7.2 и более ранних версиях параметр ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) события COM не позволял выполнить маршалинг обратно в машинный код.  Благодаря этому изменению [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) теперь успешно маршалируется.<ul><li>[x] Режим совместимости</li></ul>

#### <a name="suggestion"></a>Предложение

Если правильный маршалинг параметров ByRef SafeArray в событиях COM нарушает выполнение, этот код можно отключить, добавив следующий параметр конфигурации в файл конфигурации приложения:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.8|
|Type|Среда выполнения|
