---
ms.openlocfilehash: 53ded5ae6e5a025fc7992da099c3481587bb6f31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614902"
---
### <a name="privatefontcollectionaddfontfile-method-releases-font-resources"></a>Метод PrivateFontCollection.AddFontFile освобождает ресурсы шрифтов

#### <a name="details"></a>Подробнее

В .NET Framework 4.7.1 и предыдущих версиях класс <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> не освобождает ресурсы шрифтов GDI + после того, как <xref:System.Drawing.Text.PrivateFontCollection> удаляется для объектов <xref:System.Drawing.Font>, добавляемых в эту коллекцию с помощью метода <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)>. В платформе .NET Framework 4.7.2 и более поздних версиях класс <xref:System.Drawing.Text.FontCollection.Dispose%2A> освобождает шрифты GDI+, которые были добавлены в коллекцию как файлы.

#### <a name="suggestion"></a>Предложение

**Как принять или отклонить изменения** Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.7.2 или более поздней версии. В приложении эти изменения можно использовать одним из следующих способов:

- Выполнить повторную компиляцию, чтобы нацелить приложение на .NET Framework 4.7.2. Это изменение включено по умолчанию для приложений Windows Forms, нацеленных на .NET Framework 4.7.2 или более поздней версии.
- Оно нацелено на .NET Framework 4.7.1 и более ранние версии платформы и позволяет отказаться от функций специальных возможностей предыдущих версий путем добавления [переключателя AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) в раздел `<runtime>` файла конфигурации приложения и получения значения `false`, как показано в следующем примере.

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Drawing.Text.DoNotRemoveGdiFontsResourcesFromFontCollection=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

В приложениях, предназначенных для .NET Framework 4.7.2 или более поздней версии, где требуется сохранить предыдущие функции, можно выбрать отказ от освобождения шрифта, явно установив этот переключатель AppContext в значение `true`.

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.7.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>
- <xref:System.Drawing.Text.FontCollection.Dispose?displayProperty=nameWithType>
