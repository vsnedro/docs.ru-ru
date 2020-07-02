---
ms.openlocfilehash: ae557ce57557d027dba35b7da213c08aee85f2c7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622075"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a>ASP.NET. Исправление обработки InputAttributes и LabelAttributes для элемента управления "Флажок" в веб-формах

#### <a name="details"></a>Подробнее

Для приложений, предназначенных для .NET Framework 4.7.2 и более ранних версий, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> и <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType>, добавленные в элемент управления <xref:System.Web.UI.WebControls.CheckBox> веб-форм программными средствами, теряются после обратной передачи. Для приложений, предназначенных для .NET Framework 4.8 или более поздних версий, они сохраняются после обратной передачи.

#### <a name="suggestion"></a>Предложение

Для правильного поведения для восстановления атрибутов при обратной передаче задайте <code>targetFrameworkVersion</code> 4.8 или более позднюю версию. Пример:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Если установить значение ниже или не установить никакое значение, сохраняется старое неправильное поведение.

| name    | Значение       |
|:--------|:------------|
| Область   |Неизвестно|
|Version|4.8|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|
