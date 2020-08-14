---
ms.openlocfilehash: 2c8a5c1ec87918a91600a3557c679a42cae74896
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556345"
---
### <a name="principalpermissionattribute-is-obsolete-as-error"></a><span data-ttu-id="cb368-101">PrincipalPermissionAttribute устарел и является ошибочным</span><span class="sxs-lookup"><span data-stu-id="cb368-101">PrincipalPermissionAttribute is obsolete as error</span></span>

<span data-ttu-id="cb368-102">Конструктор <xref:System.Security.Permissions.PrincipalPermissionAttribute> устарел и вызывает ошибку времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="cb368-102">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> constructor is obsolete and produces a compile-time error.</span></span> <span data-ttu-id="cb368-103">Нельзя создать экземпляр этого атрибута или применить его к методу.</span><span class="sxs-lookup"><span data-stu-id="cb368-103">You cannot instantiate this attribute or apply it to a method.</span></span>

#### <a name="change-description"></a><span data-ttu-id="cb368-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="cb368-104">Change description</span></span>

<span data-ttu-id="cb368-105">В .NET Framework и .NET Core можно добавлять заметки к методам с помощью атрибута <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="cb368-105">On .NET Framework and .NET Core, you can annotate methods with the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute.</span></span> <span data-ttu-id="cb368-106">Пример:</span><span class="sxs-lookup"><span data-stu-id="cb368-106">For example:</span></span>

```csharp
[PrincipalPermission(SecurityAction.Demand, Role = "Administrators")]
public void MyMethod()
{
    // Code that should only run when the current user is an administrator.
}
```

<span data-ttu-id="cb368-107">Начиная с .NET 5.0 к методу нельзя применить атрибут <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="cb368-107">Starting in .NET 5.0, you cannot apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to a method.</span></span> <span data-ttu-id="cb368-108">Конструктор атрибута устарел и вызывает ошибку во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="cb368-108">The constructor for the attribute is obsolete and produces a compile-time error.</span></span> <span data-ttu-id="cb368-109">В отличие от других устаревших предупреждений, эту ошибку нельзя обойти.</span><span class="sxs-lookup"><span data-stu-id="cb368-109">Unlike other obsoletion warnings, you can't suppress the error.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="cb368-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="cb368-110">Reason for change</span></span>

<span data-ttu-id="cb368-111">Тип <xref:System.Security.Permissions.PrincipalPermissionAttribute>, как и другие типы, являющиеся подклассом <xref:System.Security.Permissions.SecurityAttribute>, является частью инфраструктуры .NET по управлению доступом для кода (CAS).</span><span class="sxs-lookup"><span data-stu-id="cb368-111">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> type, like other types that subclass <xref:System.Security.Permissions.SecurityAttribute>, is part of .NET's Code Access Security (CAS) infrastructure.</span></span> <span data-ttu-id="cb368-112">В .NET Framework 2.x-4.x среда выполнения применяет заметки <xref:System.Security.Permissions.PrincipalPermissionAttribute> к записи метода, даже если приложение выполняется с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="cb368-112">In .NET Framework 2.x - 4.x, the runtime enforces <xref:System.Security.Permissions.PrincipalPermissionAttribute> annotations on method entry, even if the application is running under a full-trust scenario.</span></span> <span data-ttu-id="cb368-113">В .NET Core и .NET 5.0 и более поздних версий не поддерживаются атрибуты CAS, и среда выполнения их игнорирует.</span><span class="sxs-lookup"><span data-stu-id="cb368-113">.NET Core and .NET 5.0 and later don't support CAS attributes, and the runtime ignores them.</span></span>

<span data-ttu-id="cb368-114">Это различие в поведении .NET Framework по отношению к .NET Core и .NET 5.0 может привести к ситуации "ошибочное открытие", когда доступ должен быть заблокирован, а вместо этого он был разрешен.</span><span class="sxs-lookup"><span data-stu-id="cb368-114">This difference in behavior from .NET Framework to .NET Core and .NET 5.0 can result in a "fail open" scenario, where access should have been blocked but instead has been allowed.</span></span> <span data-ttu-id="cb368-115">Чтобы не допустить ситуации "ошибочное открытие", больше нельзя применять этот атрибут в коде, предназначенном для .NET 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="cb368-115">To prevent the "fail open" scenario, you can no longer apply the attribute in code that targets .NET 5.0 or later.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cb368-116">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="cb368-116">Version introduced</span></span>

<span data-ttu-id="cb368-117">5.0 (предварительная версия 7)</span><span class="sxs-lookup"><span data-stu-id="cb368-117">5.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cb368-118">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="cb368-118">Recommended action</span></span>

<span data-ttu-id="cb368-119">При возникновении ошибки устаревшего атрибута необходимо выполнить определенные действия.</span><span class="sxs-lookup"><span data-stu-id="cb368-119">If you encounter the obsoletion error, you must take action.</span></span>

- <span data-ttu-id="cb368-120">**При применении атрибута к методу действия MVC ASP.NET:**</span><span class="sxs-lookup"><span data-stu-id="cb368-120">**If you're applying the attribute to an ASP.NET MVC action method:**</span></span>

  <span data-ttu-id="cb368-121">Рассмотрите возможность использования встроенной инфраструктуры авторизации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cb368-121">Consider using ASP.NET's built-in authorization infrastructure.</span></span> <span data-ttu-id="cb368-122">В следующем примере кода показано, как добавить к контроллеру атрибут <xref:System.Web.Mvc.AuthorizeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="cb368-122">The following code demonstrates how to annotate a controller with an <xref:System.Web.Mvc.AuthorizeAttribute> attribute.</span></span> <span data-ttu-id="cb368-123">Среда выполнения ASP.NET выполнит авторизацию пользователя перед выполнением действия.</span><span class="sxs-lookup"><span data-stu-id="cb368-123">The ASP.NET runtime will authorize the user before performing the action.</span></span>

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

  <span data-ttu-id="cb368-124">Дополнительные сведения см. в статьях [Авторизация на основе ролей в ASP.NET Core](/aspnet/core/security/authorization/roles) и [Общие сведения об авторизации в ASP.NET Core](/aspnet/core/security/authorization/introduction).</span><span class="sxs-lookup"><span data-stu-id="cb368-124">For more information, see [Role-based authorization in ASP.NET Core](/aspnet/core/security/authorization/roles) and [Introduction to authorization in ASP.NET Core](/aspnet/core/security/authorization/introduction).</span></span>

- <span data-ttu-id="cb368-125">**При применении атрибута к коду библиотеки вне контекста веб-приложения:**</span><span class="sxs-lookup"><span data-stu-id="cb368-125">**If you're applying the attribute to library code outside the context of a web app:**</span></span>

  <span data-ttu-id="cb368-126">Выполните проверки вручную в начале метода.</span><span class="sxs-lookup"><span data-stu-id="cb368-126">Perform the checks manually at the beginning of your method.</span></span> <span data-ttu-id="cb368-127">Это можно сделать с помощью метода <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cb368-127">This can be done by using the <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> method.</span></span>

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

#### <a name="category"></a><span data-ttu-id="cb368-128">Категория</span><span class="sxs-lookup"><span data-stu-id="cb368-128">Category</span></span>

- <span data-ttu-id="cb368-129">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="cb368-129">Core .NET libraries</span></span>
- <span data-ttu-id="cb368-130">Безопасность</span><span class="sxs-lookup"><span data-stu-id="cb368-130">Security</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cb368-131">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="cb368-131">Affected APIs</span></span>

- <xref:System.Security.Permissions.PrincipalPermissionAttribute?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Permissions.PrincipalPermissionAttribute`

-->
