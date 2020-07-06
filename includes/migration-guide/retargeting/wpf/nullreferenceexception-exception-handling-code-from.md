---
ms.openlocfilehash: 9c9c4ec55143ef991e9b69a389e0f3368263bb4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614846"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a>NullReferenceException в коде обработки исключений из ImageSourceConverter.ConvertFrom

#### <a name="details"></a>Подробнее

Ошибка в коде обработки исключений для <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> вызывала некорректное исключение <xref:System.NullReferenceException?displayProperty=fullName> вместо предполагаемого исключения (<xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> или <xref:System.IO.FileNotFoundException?displayProperty=fullName>). Это изменение устраняет эту ошибку. Теперь метод вызывает правильное исключение. <p/>По умолчанию все приложения, предназначенные для .NET Framework 4.6.2 и более ранних версий, по-прежнему вызывают исключение <xref:System.NullReferenceException?displayProperty=fullName> для обеспечения совместимости. Разработчики приложений, предназначенных для .NET Framework 4.7 и более поздних версий, должны видеть правильные исключения.

#### <a name="suggestion"></a>Предложение

Разработчики, желающие по-прежнему получать <xref:System.NullReferenceException?displayProperty=fullName> при работе с .NET Framework 4.7 и более поздних версий, могут добавить следующее в файл App.config приложения:

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.7         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType>
