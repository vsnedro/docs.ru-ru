---
title: Ошибка SYSLIB0002
description: Сведения об устаревших элементах, которые приводят к появлению ошибки во время компиляции SYSLIB0002.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 53eb51d5e525c463e5698710bdb6fa0c0907e43c
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440781"
---
# <a name="syslib0002-principalpermissionattribute-is-obsolete"></a>SYSLIB0002. PrincipalPermissionAttribute устарел

Начиная с версии .NET 5.0, конструктор <xref:System.Security.Permissions.PrincipalPermissionAttribute> является устаревшим и вызывает ошибку времени компиляции `SYSLIB0002`. Нельзя создать экземпляр этого атрибута или применить его к методу.

В отличие от других устаревших предупреждений, эту ошибку нельзя обойти.

## <a name="workarounds"></a>Обходные пути

- При применении атрибута к методу действия MVC ASP.NET:

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

- При применении атрибута к коду библиотеки вне контекста веб-приложения:

  Выполните проверки вручную в начале метода, вызвав метод <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType>.

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

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>См. также

- [PrincipalPermissionAttribute устарел и является ошибочным](3.1-5.0.md#principalpermissionattribute-is-obsolete-as-error)
