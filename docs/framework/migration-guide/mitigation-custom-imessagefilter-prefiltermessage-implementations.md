---
title: 'Устранение рисков: реализации пользовательских IMessageFilter.PreFilterMessage'
description: Узнайте о пользовательской реализации IMessageFilter.PreFilterMessage, входящей в приложения Windows Forms, предназначенные для .NET Framework 4.6.1 и более поздних версий.
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
ms.openlocfilehash: 5fe7500d3ed6ff293514495df150a747e7946dda
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475259"
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a>Устранение рисков. Пользовательские реализации IMessageFilter.PreFilterMessage

В приложениях Windows Forms, нацеленных на .NET Framework старше версии .NET Framework 4.6.1 включительно, пользовательская реализация <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> может безопасно фильтровать сообщения при вызове метода <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>, если реализация <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>:

- выполняет одно или оба следующих действия:

  - добавляет фильтр сообщений путем вызова метода <xref:System.Windows.Forms.Application.AddMessageFilter%2A>,

  - удаляет фильтр сообщений путем вызова метода <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>, метод.

- **а также** передает сообщения путем вызова метода <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>.

## <a name="impact"></a>Последствия

Это изменение затрагивает только приложения Windows Forms, предназначенные для .NET Framework, начиная с версии .NET Framework 4.6.1.

В приложениях Windows Forms, которые предназначены для более ранних версий платформы .NET Framework, такие реализации в некоторых случаях создают исключение <xref:System.IndexOutOfRangeException> при вызове метода <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>.

## <a name="mitigation"></a>Устранение рисков

Если это изменение нежелательно, его можно отключить для приложений, предназначенных для .NET Framework 4.6.1 или более поздних версий, добавив в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения следующий параметр:

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />
</runtime>
```

Кроме того, это поведение можно включить для приложений, предназначенных для предыдущих версий .NET Framework, но работающих под управлением .NET Framework 4.6.1 или более поздних версий. Для этого добавьте в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения следующий параметр:

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />
</runtime>
```

## <a name="see-also"></a>См. также

- [Совместимость приложений](application-compatibility.md)
