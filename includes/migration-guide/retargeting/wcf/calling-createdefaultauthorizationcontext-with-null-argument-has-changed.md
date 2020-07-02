---
ms.openlocfilehash: c5a061dffa1deb66e1769d6ec70dfa2155ac6a31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615767"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>Был изменен вызов метода CreateDefaultAuthorizationContext с аргументом NULL

#### <a name="details"></a>Подробнее

В .NET Framework 4.6 изменилась реализация <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName>, возвращаемая вызовом к <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName> с нулевым аргументом authorizationPolicies.

#### <a name="suggestion"></a>Предложение

В редких случаях в приложениях WCF, которые используют настраиваемую проверку подлинности, могут возникать различия в поведении. В таких случаях прежнее поведение можно восстановить двумя способами.

- Перекомпилируйте приложение для ориентации на версию .NET Framework, предшествующую 4.6. Для служб, размещенных в IIS, используйте элемент `<httpRuntime targetFramework="x.x">` для выбора более ранней версии .NET Framework в качестве целевой платформы.
- Добавьте следующую строку в раздел `<appSettings>` файла app.config.

    ```xml
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />
    ```

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.6         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType>
