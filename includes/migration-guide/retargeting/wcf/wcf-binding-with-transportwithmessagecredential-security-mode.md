---
ms.openlocfilehash: 0e949cbdeda99dd7b94e919b903a21171a57f527
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614729"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a>Привязка WCF с режимом безопасности TransportWithMessageCredential

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.6.1 привязку WCF, которая использует режим безопасности TransportWithMessageCredential, можно настроить для получения сообщений с неподписанными заголовками &quot;to&quot; для асимметричных ключей безопасности. По умолчанию неподписанные заголовки &quot;to&quot; будут отклоняться в .NET Framework 4.6.1. Они будут приниматься только в случае перевода приложения на новый режим с помощью переключателя конфигурации Switch.System.ServiceModel.AllowUnsignedToHeader.

#### <a name="suggestion"></a>Предложение

Поскольку это возможность, включаемая пользователем, она не должна влиять на поведение существующих приложений.<br/>Для включения или отключения нового поведения используйте следующий параметр конфигурации:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />
</runtime>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Прозрачный |
| Version | 4.6.1       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
