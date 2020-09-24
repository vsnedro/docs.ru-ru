---
ms.openlocfilehash: e8b98e465228afd07432e737bb16aefb1b979973
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770820"
---
### <a name="wcf-addressheadercollection-now-throws-an-argumentexception-if-an-addressheader-element-is-null"></a>WCF AddressHeaderCollection теперь создает исключение ArgumentException, если элемент addressHeader равен NULL

#### <a name="details"></a>Подробнее

Начиная с версии .NET Framework 4.7.1, конструктор <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> создает исключение <xref:System.ArgumentException>, если один из элементов равен `null`. В версии .NET Framework 4.7 и более ранних исключение не создается.

#### <a name="suggestion"></a>Предложение

Если из-за этого изменения в .NET Framework 4.7.1 или более поздних версий вы сталкиваетесь с проблемами совместимости, вы можете отключить его, добавив следующую строку в раздел `<runtime>` файла app.config:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableAddressHeaderCollectionValidation=true" />
  </runtime>
</configuration>

| Name    | Value   |
|:--------|:--------|
| Scope   | Minor   |
| Version | 4.7.1   |
| Type    | Runtime |

#### Affected APIs

- <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})>

<!--

#### Affected APIs

- `M:System.ServiceModel.Channels.AddressHeaderCollection.#ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})`

-->
