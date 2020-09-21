---
ms.openlocfilehash: c64431fd651fd7d53fb46231c6acc10c5cb43fff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606351"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a>Действия upbutton и downbutton домена WinForm теперь синхронизированы

#### <a name="details"></a>Подробнее

В .NET Framework 4.7.1 и предыдущих версиях действие <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> элемента управления <xref:System.Windows.Forms.DomainUpDown> игнорируется, если присутствует текст элемента управления, и разработчику приходится использовать действие <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> для элемента управления перед использованием действия <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>. Начиная с .NET Framework 4.7.2 оба действия, <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> и <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>, работают независимо друг от друга в этом сценарии и остаются синхронизированными.

#### <a name="suggestion"></a>Предложение

Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.7.2 или более поздней версии. В приложении эти изменения можно использовать одним из следующих способов:

- Выполнить повторную компиляцию, чтобы нацелить приложение на .NET Framework 4.7.2. Это изменение включено по умолчанию для приложений Windows Forms, нацеленных на .NET Framework 4.7.2 или более поздней версии.
- Для отказа от функций прокрутки предыдущих версий [переключатель AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) добавляется в раздел `<runtime>` файла конфигурации приложения и получает значение `false`, как показано в следующем примере.

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.7.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
