---
ms.openlocfilehash: b88f7d4a17f885b687d99ab9410a56039e176080
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614640"
---
### <a name="calls-to-claimsidentity-constructors"></a>Вызовы к конструкторам ClaimsIdentity

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.6.2 конструкторы <xref:System.Security.Claims.ClaimsIdentity> с параметром <xref:System.Security.Principal.IIdentity?displayProperty=fullName> иначе задают свойство <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>. Если аргумент <xref:System.Security.Principal.IIdentity?displayProperty=fullName> является объектом <xref:System.Security.Claims.ClaimsIdentity>, а свойство <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> этого объекта <xref:System.Security.Claims.ClaimsIdentity> не равно `null`, свойство <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> присоединяется с помощью метода <xref:System.Security.Claims.ClaimsIdentity.Clone>. В Framework 4.6.1 и более ранних версиях свойство <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> прикреплено как существующая ссылка. В результате этого изменения, начиная с .NET Framework 4.6.2, свойство <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> нового объекта <xref:System.Security.Claims.ClaimsIdentity> не равно свойству <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> аргумента конструктора <xref:System.Security.Principal.IIdentity?displayProperty=fullName>. В .NET Framework 4.6.1 и более ранних версиях они равны.

#### <a name="suggestion"></a>Предложение

Если такое поведение нежелательно, можно восстановить прежнее поведение, задав переключателю `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` в файле конфигурации приложения значение `true`. Для этого требуется добавить следующую информацию в раздел `<runtime>` файла web.config:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />
  </runtime>
</configuration>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.6.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity)>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim})>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim},System.String,System.String,System.String)>
