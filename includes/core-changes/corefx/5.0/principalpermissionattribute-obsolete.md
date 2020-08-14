---
ms.openlocfilehash: 2c8a5c1ec87918a91600a3557c679a42cae74896
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556345"
---
### <a name="principalpermissionattribute-is-obsolete-as-error"></a>PrincipalPermissionAttribute устарел и является ошибочным

Конструктор <xref:System.Security.Permissions.PrincipalPermissionAttribute> устарел и вызывает ошибку времени компиляции. Нельзя создать экземпляр этого атрибута или применить его к методу.

#### <a name="change-description"></a>Описание изменений

В .NET Framework и .NET Core можно добавлять заметки к методам с помощью атрибута <xref:System.Security.Permissions.PrincipalPermissionAttribute>. Пример:

```csharp
[PrincipalPermission(SecurityAction.Demand, Role = "Administrators")]
public void MyMethod()
{
    // Code that should only run when the current user is an administrator.
}
```

Начиная с .NET 5.0 к методу нельзя применить атрибут <xref:System.Security.Permissions.PrincipalPermissionAttribute>. Конструктор атрибута устарел и вызывает ошибку во время компиляции. В отличие от других устаревших предупреждений, эту ошибку нельзя обойти.

#### <a name="reason-for-change"></a>Причина изменения

Тип <xref:System.Security.Permissions.PrincipalPermissionAttribute>, как и другие типы, являющиеся подклассом <xref:System.Security.Permissions.SecurityAttribute>, является частью инфраструктуры .NET по управлению доступом для кода (CAS). В .NET Framework 2.x-4.x среда выполнения применяет заметки <xref:System.Security.Permissions.PrincipalPermissionAttribute> к записи метода, даже если приложение выполняется с полным доверием. В .NET Core и .NET 5.0 и более поздних версий не поддерживаются атрибуты CAS, и среда выполнения их игнорирует.

Это различие в поведении .NET Framework по отношению к .NET Core и .NET 5.0 может привести к ситуации "ошибочное открытие", когда доступ должен быть заблокирован, а вместо этого он был разрешен. Чтобы не допустить ситуации "ошибочное открытие", больше нельзя применять этот атрибут в коде, предназначенном для .NET 5.0 и более поздних версий.

#### <a name="version-introduced"></a>Представленная версия

5.0 (предварительная версия 7)

#### <a name="recommended-action"></a>Рекомендованное действие

При возникновении ошибки устаревшего атрибута необходимо выполнить определенные действия.

- **При применении атрибута к методу действия MVC ASP.NET:**

  Рассмотрите возможность использования встроенной инфраструктуры авторизации ASP.NET. В следующем примере кода показано, как добавить к контроллеру атрибут <xref:System.Web.Mvc.AuthorizeAttribute>. Среда выполнения ASP.NET выполнит авторизацию пользователя перед выполнением действия.

  ```csharp
  using Microsoft.AspNetCore.Authorization;

  namespace MySampleApp
  {
      [Authorize(Roles = "Administrator")]
      public class AdministrationController : Controller
      {
          public ActionResult MyAction()
          {
              // This code won't run unless the current user
              // is in the 'Administrator' role.
          }
      }
  }
  ```

  Дополнительные сведения см. в статьях [Авторизация на основе ролей в ASP.NET Core](/aspnet/core/security/authorization/roles) и [Общие сведения об авторизации в ASP.NET Core](/aspnet/core/security/authorization/introduction).

- **При применении атрибута к коду библиотеки вне контекста веб-приложения:**

  Выполните проверки вручную в начале метода. Это можно сделать с помощью метода <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType>.

  ```csharp
  using System.Threading;

  void DoSomething()
  {
      if (Thread.CurrentPrincipal == null
          || !Thread.CurrentPrincipal.IsInRole("Administrators"))
      {
          throw new Exception("User is anonymous or isn't an admin.");
      }

      // Code that should run only when user is an administrator.
  }
  ```

#### <a name="category"></a>Категория

- Библиотеки Core .NET
- Безопасность

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Security.Permissions.PrincipalPermissionAttribute?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Permissions.PrincipalPermissionAttribute`

-->
