---
ms.openlocfilehash: 9b184f54650d2efb31ec66f443198b19ceaeb5f3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614705"
---
### <a name="applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>Application.FilterMessage больше не создает исключение для реализаций IMessageFilter.PreFilterMessage с повторным входом

#### <a name="details"></a>Подробнее

До версии .NET Framework 4.6.1 при вызове <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> с <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)>, вызывающим <xref:System.Windows.Forms.Application.AddMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName> или <xref:System.Windows.Forms.Application.RemoveMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName> (с одновременным вызовом <xref:System.Windows.Forms.Application.DoEvents>), возникало исключение <xref:System.IndexOutOfRangeException?displayProperty=fullName>.<p/>Начиная с приложений, предназначенных для .NET Framework 4.6.1, это исключение больше не создается, и можно использовать фильтры с повторным входом, как описано выше.

#### <a name="suggestion"></a>Предложение

Имейте в виду, что <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> больше не вызывает исключение для поведения <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> с повторным входом, как описано выше. Будут затронуты только приложения, предназначенные для .NET Framework 4.6.1. В приложениях, предназначенных для .NET Framework 4.6.1, можно отказаться от этого изменения (или в приложениях, предназначенных для более старых платформ, можно использовать изменение) с помощью параметра совместимости [DontSupportReentrantFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md#mitigation).

| name          | Значение       |
|:--------------|:------------|
| Область         | Пограничный случай        |
| Version       | 4.6.1       |
| Type          | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)?displayProperty=nameWithType>
