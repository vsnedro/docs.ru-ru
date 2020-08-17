---
title: 'Безопасность: проверка подлинности и авторизация в веб-формах ASP.NET и Blazor'
description: Узнайте, как выполнять проверку подлинности и авторизацию в веб-формах ASP.NET и Blazor .
author: ardalis
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/11/2019
ms.openlocfilehash: 1cc82b14a940465c26377f9181a2e20b46b0783f
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267870"
---
# <a name="security-authentication-and-authorization-in-aspnet-web-forms-and-no-locblazor"></a><span data-ttu-id="1d747-103">Безопасность: проверка подлинности и авторизация в веб-формах ASP.NET и Blazor</span><span class="sxs-lookup"><span data-stu-id="1d747-103">Security: Authentication and Authorization in ASP.NET Web Forms and Blazor</span></span>

<span data-ttu-id="1d747-104">Миграция из приложения веб-форм ASP.NET в Blazor почти наверняка требует обновления проверки подлинности и авторизации, предполагая, что для приложения настроена проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="1d747-104">Migrating from an ASP.NET Web Forms application to Blazor will almost certainly require updating how authentication and authorization is performed, assuming the application had authentication configured.</span></span> <span data-ttu-id="1d747-105">В этой главе рассматривается миграция из модели универсального поставщика веб-форм ASP.NET (для членства, ролей и профилей пользователей) и работа с удостоверениями ASP.NET Core из Blazor приложений.</span><span class="sxs-lookup"><span data-stu-id="1d747-105">This chapter will cover how to migrate from the ASP.NET Web Forms universal provider model (for membership, roles, and user profiles) and how to work with ASP.NET Core Identity from Blazor apps.</span></span> <span data-ttu-id="1d747-106">Хотя в этой главе рассматриваются основные этапы и рекомендации, подробные инструкции и сценарии можно найти в документации, на которую имеются ссылки.</span><span class="sxs-lookup"><span data-stu-id="1d747-106">While this chapter will cover the high level steps and considerations, the detailed steps and scripts may be found in the referenced documentation.</span></span>

## <a name="aspnet-universal-providers"></a><span data-ttu-id="1d747-107">Универсальные поставщики ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1d747-107">ASP.NET universal providers</span></span>

<span data-ttu-id="1d747-108">Начиная с ASP.NET 2,0 платформа веб-форм ASP.NET поддерживала модель поставщика для различных функций, включая членство.</span><span class="sxs-lookup"><span data-stu-id="1d747-108">Since ASP.NET 2.0, the ASP.NET Web Forms platform has supported a provider model for a variety of features, including membership.</span></span> <span data-ttu-id="1d747-109">Поставщик универсального членства вместе с дополнительным поставщиком ролей очень часто развертывается с помощью приложений ASP.NET Web Forms.</span><span class="sxs-lookup"><span data-stu-id="1d747-109">The universal membership provider, along with the optional role provider, is very commonly deployed with ASP.NET Web Forms applications.</span></span> <span data-ttu-id="1d747-110">Он обеспечивает надежный и безопасный способ управления проверкой подлинности и авторизацией, которая будет работать уже сегодня.</span><span class="sxs-lookup"><span data-stu-id="1d747-110">It offers a robust and secure way to manage authentication and authorization that continues to work well today.</span></span> <span data-ttu-id="1d747-111">Последнее предложение этих универсальных поставщиков доступно в виде пакета NuGet, [Microsoft. AspNet. Providers](https://www.nuget.org/packages/Microsoft.AspNet.Providers).</span><span class="sxs-lookup"><span data-stu-id="1d747-111">The most recent offering of these universal providers is available as a NuGet package, [Microsoft.AspNet.Providers](https://www.nuget.org/packages/Microsoft.AspNet.Providers).</span></span>

<span data-ttu-id="1d747-112">Универсальные поставщики работать с схемой базы данных SQL, которая включает такие таблицы `aspnet_Applications` , как,, `aspnet_Membership` `aspnet_Roles` и `aspnet_Users` .</span><span class="sxs-lookup"><span data-stu-id="1d747-112">The Universal Providers work with a SQL database schema that includes tables like `aspnet_Applications`, `aspnet_Membership`, `aspnet_Roles`, and `aspnet_Users`.</span></span> <span data-ttu-id="1d747-113">При настройке с помощью [ командыaspnet_regsql.exe](https://docs.microsoft.com/previous-versions/ms229862(v=vs.140))поставщики устанавливают таблицы и хранимые процедуры, которые предоставляют все необходимые запросы и команды, необходимые для работы с базовыми данными.</span><span class="sxs-lookup"><span data-stu-id="1d747-113">When configured by running the [aspnet_regsql.exe command](https://docs.microsoft.com/previous-versions/ms229862(v=vs.140)), the providers install tables and stored procedures that provide all of the necessary queries and commands necessary to work with the underlying data.</span></span> <span data-ttu-id="1d747-114">Схема базы данных и эти хранимые процедуры несовместимы с более новыми ASP.NET Identity и ASP.NET Core системами удостоверений, поэтому существующие данные должны быть перенесены в новую систему.</span><span class="sxs-lookup"><span data-stu-id="1d747-114">The database schema and these stored procedures are not compatible with newer ASP.NET Identity and ASP.NET Core Identity systems, so existing data must be migrated into the new system.</span></span> <span data-ttu-id="1d747-115">На рис. 1 показан пример схемы таблицы, настроенной для универсальных поставщиков.</span><span class="sxs-lookup"><span data-stu-id="1d747-115">Figure 1 shows an example table schema configured for universal providers.</span></span>

![Схема универсальных поставщиков](./media/security/membership-tables.png)

<span data-ttu-id="1d747-117">Универсальный поставщик обрабатывает пользователей, членство, роли и профили.</span><span class="sxs-lookup"><span data-stu-id="1d747-117">The universal provider handles users, membership, roles, and profiles.</span></span> <span data-ttu-id="1d747-118">Пользователям назначаются глобально уникальные идентификаторы и очень основные сведения (userId, userName) хранятся в `aspnet_Users` таблице.</span><span class="sxs-lookup"><span data-stu-id="1d747-118">Users are assigned globally unique identifiers and very basic information (userId, userName) is stored in the `aspnet_Users` table.</span></span> <span data-ttu-id="1d747-119">Сведения о проверке подлинности, такие как пароль, формат пароля, Salt пароля, счетчики блокировки и сведения и т. д., хранятся в `aspnet_Membership` таблице.</span><span class="sxs-lookup"><span data-stu-id="1d747-119">Authentication information, such as password, password format, password salt, lockout counters and details, etc. are stored in the `aspnet_Membership` table.</span></span> <span data-ttu-id="1d747-120">Роли состоят только из имен и уникальных идентификаторов, которые назначаются пользователям через `aspnet_UsersInRoles` таблицу взаимосвязей, предоставляя связь «многие ко многим».</span><span class="sxs-lookup"><span data-stu-id="1d747-120">Roles consist simply of names and unique identifiers, which are assigned to users via the `aspnet_UsersInRoles` association table, providing a many-to-many relationship.</span></span>

<span data-ttu-id="1d747-121">Если существующая система использует роли в дополнение к членству, необходимо перенести учетные записи пользователей, связанные пароли, роли и членство в роли в ASP.NET Core удостоверение.</span><span class="sxs-lookup"><span data-stu-id="1d747-121">If your existing system is using roles in addition to membership, you will need to migrate the user accounts, the associated passwords, the roles, and the role membership into ASP.NET Core Identity.</span></span> <span data-ttu-id="1d747-122">Вам также, скорее всего, потребуется обновить код, в котором выполняется проверка ролей с помощью инструкций If, вместо этого использовать декларативные фильтры, атрибуты и (или) вспомогательные функции тегов.</span><span class="sxs-lookup"><span data-stu-id="1d747-122">You will also most likely need to update your code where you're currently performing role checks using if statements to instead leverage declarative filters, attributes, and/or tag helpers.</span></span> <span data-ttu-id="1d747-123">В конце этой главы мы рассмотрим рекомендации по миграции более подробно.</span><span class="sxs-lookup"><span data-stu-id="1d747-123">We will review migration considerations in greater detail at the end of this chapter.</span></span>

### <a name="authorization-configuration-in-web-forms"></a><span data-ttu-id="1d747-124">Настройка авторизации в веб-формах</span><span class="sxs-lookup"><span data-stu-id="1d747-124">Authorization configuration in Web Forms</span></span>

<span data-ttu-id="1d747-125">Чтобы настроить Полномочный доступ к определенным страницам в приложении веб-форм ASP.NET, обычно вы указываете, что определенные страницы или папки недоступны для анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="1d747-125">To configure authorized access to certain pages in an ASP.NET Web Forms application, typically you specify that certain pages or folders are inaccessible to anonymous users.</span></span> <span data-ttu-id="1d747-126">Это делается в файле web.config:</span><span class="sxs-lookup"><span data-stu-id="1d747-126">This is done in the web.config file:</span></span>

```xml
<?xml version="1.0"?>
<configuration>
    <system.web>
      <authentication mode="Forms">
        <forms defaultUrl="~/home.aspx" loginUrl="~/login.aspx"
          slidingExpiration="true" timeout="2880"></forms>
      </authentication>

      <authorization>
        <deny users="?" />
      </authorization>
    </system.web>
</configuration>
```

<span data-ttu-id="1d747-127">В `authentication` разделе конфигурации настраивается проверка подлинности с помощью форм для приложения.</span><span class="sxs-lookup"><span data-stu-id="1d747-127">The `authentication` configuration section sets up forms authentication for the application.</span></span> <span data-ttu-id="1d747-128">`authorization`Раздел используется для запрета анонимных пользователей для всего приложения.</span><span class="sxs-lookup"><span data-stu-id="1d747-128">The `authorization` section is used to disallow anonymous users for the entire application.</span></span> <span data-ttu-id="1d747-129">Однако можно предоставить более детализированные правила авторизации для каждого расположения, а также применить проверки авторизации на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="1d747-129">However, you can provide more granular authorization rules on a per-location basis as well as apply role based authorization checks.</span></span>

```xml
<location path="login.aspx">
  <system.web>
    <authorization>
      <allow users="*" />
    </authorization>
  </system.web>
</location>
```

<span data-ttu-id="1d747-130">Приведенная выше конфигурация при объединении с первой позволяет анонимным пользователям получать доступ к странице входа, переопределяя ограничение на уровне сайта для пользователей, не прошедших проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="1d747-130">The above configuration, when combined with the first one, would allow anonymous users to access the login page, overriding the site-wide restriction on non-authenticated users.</span></span>

```xml
<location path="/admin">
  <system.web>
    <authorization>
      <allow roles="Administrators" />
      <deny users="*" />
    </authorization>
  </system.web>
</location>
```

<span data-ttu-id="1d747-131">Приведенная выше конфигурация, в сочетании с другими, позволяет ограничивать доступ к `/admin` папке и всем ее ресурсам членам роли "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="1d747-131">The above configuration, when combined with the others, restricts access to the `/admin` folder and all resources within it to members of the "Administrators" role.</span></span> <span data-ttu-id="1d747-132">Это также можно применить, поместив отдельный `web.config` файл в `/admin` корневую папку.</span><span class="sxs-lookup"><span data-stu-id="1d747-132">This could also be applied by placing a separate `web.config` file within the `/admin` folder root.</span></span>

### <a name="authorization-code-in-web-forms"></a><span data-ttu-id="1d747-133">Код авторизации в веб-формах</span><span class="sxs-lookup"><span data-stu-id="1d747-133">Authorization code in Web Forms</span></span>

<span data-ttu-id="1d747-134">Помимо настройки доступа с помощью `web.config` , можно также программно настроить доступ и поведение в приложении веб-форм.</span><span class="sxs-lookup"><span data-stu-id="1d747-134">In addition to configuring access using `web.config`, you can also programmatically configure access and behavior in your Web Forms application.</span></span> <span data-ttu-id="1d747-135">Например, можно ограничить возможность выполнения определенных операций или просмотра определенных данных в зависимости от роли пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d747-135">For instance, you can restrict the ability to perform certain operations or view certain data based on the user's role.</span></span>

<span data-ttu-id="1d747-136">Этот код можно использовать как в логике CodeBehind, так и на самой странице:</span><span class="sxs-lookup"><span data-stu-id="1d747-136">This code can be used both in codebehind logic as well as in the page itself:</span></span>

```html
<% if (HttpContext.Current.User.IsInRole("Administrators")) { %>
  <a href="/admin">Go To Admin</a>
<% } %>
```

<span data-ttu-id="1d747-137">Помимо проверки членства в роли пользователя, можно также определить, прошли ли они проверку подлинности (хотя часто это лучше выполнить с использованием конфигурации на основе расположения, описанной выше).</span><span class="sxs-lookup"><span data-stu-id="1d747-137">In addition to checking user role membership, you can also determine if they are authenticated (though often this is better done using the location-based configuration covered above).</span></span> <span data-ttu-id="1d747-138">Ниже приведен пример такого подхода.</span><span class="sxs-lookup"><span data-stu-id="1d747-138">Below is an example of this approach.</span></span>

```csharp
protected void Page_Load(object sender, EventArgs e)
{
    if (!User.Identity.IsAuthenticated)
    {
        FormsAuthentication.RedirectToLoginPage();
    }
    if (!Roles.IsUserInRole(User.Identity.Name, "Administrators"))
    {
        MessageLabel.Text = "Only administrators can view this.";
        SecretPanel.Visible = false;
    }
}
```

<span data-ttu-id="1d747-139">В приведенном выше коде управление доступом на основе ролей (RBAC) используется для определения того, видимы ли определенные элементы страницы, например, в `SecretPanel` зависимости от роли текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d747-139">In the code above, role-based access control (RBAC) is used to determine whether certain elements of the page, such as a `SecretPanel`, are visible based on the current user's role.</span></span>

<span data-ttu-id="1d747-140">Как правило, приложения ASP.NET Web Forms настраивают безопасность в `web.config` файле, а затем добавляют дополнительные проверки, если это необходимо на `.aspx` страницах и связанных с ними `.aspx.cs` файлах кода поддержки.</span><span class="sxs-lookup"><span data-stu-id="1d747-140">Typically, ASP.NET Web Forms applications configure security within the `web.config` file and then add additional checks where needed in `.aspx` pages and their related `.aspx.cs` codebehind files.</span></span> <span data-ttu-id="1d747-141">Большинство приложений используют универсального поставщика членства, часто с дополнительным поставщиком ролей.</span><span class="sxs-lookup"><span data-stu-id="1d747-141">Most applications leverage the universal membership provider, frequently with the additional role provider.</span></span>

## <a name="aspnet-core-identity"></a><span data-ttu-id="1d747-142">Идентификация ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1d747-142">ASP.NET Core Identity</span></span>

<span data-ttu-id="1d747-143">Несмотря на то, что по-прежнему выполняется проверка подлинности и авторизация, ASP.NET Core удостоверение использует другой набор абстракций и допущений по сравнению с универсальными поставщиками.</span><span class="sxs-lookup"><span data-stu-id="1d747-143">Although still tasked with authentication and authorization, ASP.NET Core Identity uses a different set of abstractions and assumptions when compared to the universal providers.</span></span> <span data-ttu-id="1d747-144">Например, Новая модель удостоверений поддерживает проверку подлинности третьих сторон, позволяя пользователям проходить проверку подлинности с помощью учетной записи социальных сетей или другого доверенного поставщика проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1d747-144">For example, the new Identity model supports third party authentication, allowing users to authenticate using a social media account or other trusted authentication provider.</span></span> <span data-ttu-id="1d747-145">ASP.NET Core Identity поддерживает пользовательский интерфейс для часто необходимых страниц, таких как вход, выход и регистрация.</span><span class="sxs-lookup"><span data-stu-id="1d747-145">ASP.NET Core Identity supports UI for commonly needed pages like login, logout, and register.</span></span> <span data-ttu-id="1d747-146">Он использует EF Core для доступа к данным, а EF Core миграции для создания необходимой схемы, необходимой для поддержки ее модели данных.</span><span class="sxs-lookup"><span data-stu-id="1d747-146">It leverages EF Core for its data access, and uses EF Core migrations to generate the necessary schema required to supports its data model.</span></span> <span data-ttu-id="1d747-147">Это [Введение в идентификацию на ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/identity) предоставляет хороший обзор того, что входит в состав ASP.NET Core удостоверений и как приступить к работе с ним.</span><span class="sxs-lookup"><span data-stu-id="1d747-147">This [introduction to Identity on ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/identity) provides a good overview of what is included with ASP.NET Core Identity and how to get started working with it.</span></span> <span data-ttu-id="1d747-148">Если вы еще не настроили удостоверение ASP.NET Core в приложении и его базе данных, оно поможет приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="1d747-148">If you haven't already set up ASP.NET Core Identity in your application and its database, it will help you get started.</span></span>

### <a name="roles-claims-and-policies"></a><span data-ttu-id="1d747-149">Роли, утверждения и политики</span><span class="sxs-lookup"><span data-stu-id="1d747-149">Roles, claims, and policies</span></span>

<span data-ttu-id="1d747-150">Универсальные поставщики и удостоверение ASP.NET Core поддерживают концепцию ролей.</span><span class="sxs-lookup"><span data-stu-id="1d747-150">Both the universal providers and ASP.NET Core Identity support the concept of roles.</span></span> <span data-ttu-id="1d747-151">Вы можете создавать роли для пользователей и назначать им роли.</span><span class="sxs-lookup"><span data-stu-id="1d747-151">You can create roles for users and assign users to roles.</span></span> <span data-ttu-id="1d747-152">Пользователи могут принадлежать любому количеству ролей, и вы можете проверить членство в роли в рамках реализации авторизации.</span><span class="sxs-lookup"><span data-stu-id="1d747-152">Users can belong to any number of roles, and you can verify role membership as part of your authorization implementation.</span></span>

<span data-ttu-id="1d747-153">Помимо ролей, ASP.NET Core Identity поддерживает концепции заявок и политик.</span><span class="sxs-lookup"><span data-stu-id="1d747-153">In addition to roles, ASP.NET Core identity supports the concepts of claims and policies.</span></span> <span data-ttu-id="1d747-154">Хотя роль должна соответствовать набору ресурсов, доступ к которым должен иметь пользователь этой роли, утверждение — это просто часть удостоверения пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d747-154">While a role should specifically correspond to a set of resources a user in that role should be able to access, a claim is simply part of a user's identity.</span></span> <span data-ttu-id="1d747-155">Утверждение — это пара "имя-значение", которая представляет предметную тему, а не то, что может делать субъект.</span><span class="sxs-lookup"><span data-stu-id="1d747-155">A claim is a name value pair that represents what the subject is, not what the subject can do.</span></span>

<span data-ttu-id="1d747-156">Можно напрямую проверить утверждения пользователя и определить, следует ли пользователю предоставлять доступ к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="1d747-156">It is possible to directly inspect a user's claims and determine based on these whether a user should be given access to a resource.</span></span> <span data-ttu-id="1d747-157">Однако такие проверки часто повторяются и разбросаны по всей системе.</span><span class="sxs-lookup"><span data-stu-id="1d747-157">However, such checks are often repetitive and scattered throughout the system.</span></span> <span data-ttu-id="1d747-158">Лучшим подходом является определение *политики*.</span><span class="sxs-lookup"><span data-stu-id="1d747-158">A better approach is to define a *policy*.</span></span>

<span data-ttu-id="1d747-159">Политика авторизации состоит из одного или нескольких требований.</span><span class="sxs-lookup"><span data-stu-id="1d747-159">An authorization policy consists of one or more requirements.</span></span> <span data-ttu-id="1d747-160">Политики регистрируются как часть конфигурации службы авторизации в `ConfigureServices` методе `Startup.cs` .</span><span class="sxs-lookup"><span data-stu-id="1d747-160">Policies are registered as part of the authorization service configuration in the `ConfigureServices` method of `Startup.cs`.</span></span> <span data-ttu-id="1d747-161">Например, следующий фрагмент кода настраивает политику с именем "Канадиансонли", которая требует, чтобы пользователь имел утверждение страны со значением "Канада".</span><span class="sxs-lookup"><span data-stu-id="1d747-161">For example, the following code snippet configures a policy called "CanadiansOnly" which has the requirement that the user have the Country claim with the value of "Canada".</span></span>

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("CanadiansOnly", policy => policy.RequireClaim(ClaimTypes.Country, "Canada"));
});
```

<span data-ttu-id="1d747-162">[Дополнительные сведения о создании пользовательских политик см. в документации](https://docs.microsoft.com/aspnet/core/security/authorization/policies).</span><span class="sxs-lookup"><span data-stu-id="1d747-162">You can [learn more about how to create custom policies in the documentation](https://docs.microsoft.com/aspnet/core/security/authorization/policies).</span></span>

<span data-ttu-id="1d747-163">Независимо от того, используете ли вы политики или роли, вы можете указать, что конкретная страница в Blazor приложении должна иметь роль или политику с `[Authorize]` атрибутом, применяемую с `@attribute` директивой.</span><span class="sxs-lookup"><span data-stu-id="1d747-163">Whether you're using policies or roles, you can specify that a particular page in your Blazor application require that role or policy with the `[Authorize]` attribute, applied with the `@attribute` directive.</span></span>

<span data-ttu-id="1d747-164">Требования к роли:</span><span class="sxs-lookup"><span data-stu-id="1d747-164">Requiring a role:</span></span>

```csharp
@attribute [Authorize(Roles ="administrators")]
```

<span data-ttu-id="1d747-165">Требовать соблюдение политики:</span><span class="sxs-lookup"><span data-stu-id="1d747-165">Requiring a policy be satisfied:</span></span>

```csharp
@attribute [Authorize(Policy ="CanadiansOnly")]
```

<span data-ttu-id="1d747-166">Если вам требуется доступ к состоянию проверки подлинности, ролям или утверждениям пользователя в коде, существует два основных способа добиться этого.</span><span class="sxs-lookup"><span data-stu-id="1d747-166">If you need access to a user's authentication state, roles, or claims in your code, there are two primary ways to achieve this.</span></span> <span data-ttu-id="1d747-167">Первый — получение состояния проверки подлинности в виде каскадного параметра.</span><span class="sxs-lookup"><span data-stu-id="1d747-167">The first is to receive the authentication state as a cascading parameter.</span></span> <span data-ttu-id="1d747-168">Второй — доступ к состоянию с помощью внедренного `AuthenticationStateProvider` .</span><span class="sxs-lookup"><span data-stu-id="1d747-168">The second is to access the state using an injected `AuthenticationStateProvider`.</span></span> <span data-ttu-id="1d747-169">Сведения о каждом из этих подходов описаны в [ Blazor документации по безопасности](https://docs.microsoft.com/aspnet/core/blazor/security/).</span><span class="sxs-lookup"><span data-stu-id="1d747-169">The details of each of these approaches are described in the [Blazor Security documentation](https://docs.microsoft.com/aspnet/core/blazor/security/).</span></span>

<span data-ttu-id="1d747-170">В следующем коде показано, как получить в `AuthenticationState` качестве каскадного параметра:</span><span class="sxs-lookup"><span data-stu-id="1d747-170">The following code shows how to receive the `AuthenticationState` as a cascading parameter:</span></span>

```csharp
[CascadingParameter]
private Task<AuthenticationState> authenticationStateTask { get; set; }
```

<span data-ttu-id="1d747-171">С помощью этого параметра можно получить пользователя, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="1d747-171">With this parameter in place, you can get the user using this code:</span></span>

```csharp
var authState = await authenticationStateTask;
var user = authState.User;
```

<span data-ttu-id="1d747-172">В следующем коде показано, как внедрить `AuthenticationStateProvider` :</span><span class="sxs-lookup"><span data-stu-id="1d747-172">The following code shows how to inject the `AuthenticationStateProvider`:</span></span>

```csharp
@using Microsoft.AspNetCore.Components.Authorization
@inject AuthenticationStateProvider AuthenticationStateProvider
```

<span data-ttu-id="1d747-173">Используя поставщик, вы можете получить доступ к пользователю с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="1d747-173">With the provider in place, you can gain access to the user with the following code:</span></span>

```csharp
AuthenticationState authState = await AuthenticationStateProvider.GetAuthenticationStateAsync();
ClaimsPrincipal user = authState.User;

if (user.Identity.IsAuthenticated)
{
  // work with user.Claims and/or user.Roles
}
```

<span data-ttu-id="1d747-174">**Примечание.** `AuthorizeView` Компонент, рассмотренный далее в этой главе, предоставляет декларативный способ управления тем, что видит пользователь на странице или в компоненте.</span><span class="sxs-lookup"><span data-stu-id="1d747-174">**Note:** The `AuthorizeView` component, covered later in this chapter, provides a declarative way to control what a user sees on a page or component.</span></span>

<span data-ttu-id="1d747-175">Для работы с пользователями и утверждениями (в Blazor серверных приложениях) также может потребоваться внедрить `UserManager<T>` (использовать `IdentityUser` для использования по умолчанию), который можно использовать для перечисления и изменения утверждений для пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d747-175">To work with users and claims (in Blazor Server applications) you may also need to inject a `UserManager<T>` (use `IdentityUser` for default) which you can use to enumerate and modify claims for a user.</span></span> <span data-ttu-id="1d747-176">Сначала вставьте тип и присвойте его свойству:</span><span class="sxs-lookup"><span data-stu-id="1d747-176">First inject the type and assign it to a property:</span></span>

```csharp
@inject UserManager<IdentityUser> MyUserManager
```

<span data-ttu-id="1d747-177">Затем используйте его для работы с утверждениями пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d747-177">Then use it to work with the user's claims.</span></span> <span data-ttu-id="1d747-178">В следующем примере показано, как добавить и сохранить утверждение для пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d747-178">The following sample shows how to add and persist a claim on a user:</span></span>

```csharp
private async Task AddCountryClaim()
{
    var authState = await AuthenticationStateProvider.GetAuthenticationStateAsync();
    var user = authState.User;
    var identityUser = await MyUserManager.FindByNameAsync(user.Identity.Name);

    if (!user.HasClaim(c => c.Type == ClaimTypes.Country))
    {
        // stores the claim in the cookie
        ClaimsIdentity id = new ClaimsIdentity();
        id.AddClaim(new Claim(ClaimTypes.Country, "Canada"));
        user.AddIdentity(id);

        // save the claim in the database
        await MyUserManager.AddClaimAsync(identityUser, new Claim(ClaimTypes.Country, "Canada"));
    }
}
```

<span data-ttu-id="1d747-179">Если необходимо работать с ролями, используйте тот же подход.</span><span class="sxs-lookup"><span data-stu-id="1d747-179">If you need to work with roles, follow the same approach.</span></span> <span data-ttu-id="1d747-180">Может потребоваться внедрить `RoleManager<T>` (использовать `IdentityRole` для типа по умолчанию), чтобы перечислить сами роли и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="1d747-180">You may need to inject a `RoleManager<T>` (use `IdentityRole` for default type) to list and manage the roles themselves.</span></span>

<span data-ttu-id="1d747-181">**Примечание.** В Blazor проектах сборки для выполнения этих операций необходимо предоставить API-интерфейсы сервера (вместо использования `UserManager<T>` или `RoleManager<T>` непосредственно).</span><span class="sxs-lookup"><span data-stu-id="1d747-181">**Note:** In Blazor WebAssembly projects, you will need to provide server APIs to perform these operations (instead of using `UserManager<T>` or `RoleManager<T>` directly).</span></span> <span data-ttu-id="1d747-182">BlazorКлиентское приложение сборки может управлять утверждениями и (или) ролями путем безопасного вызова конечных точек API, предоставляемых для этой цели.</span><span class="sxs-lookup"><span data-stu-id="1d747-182">A Blazor WebAssembly client application would manage claims and/or roles by securely calling API endpoints exposed for this purpose.</span></span>

### <a name="migration-guide"></a><span data-ttu-id="1d747-183">Руководство по миграции</span><span class="sxs-lookup"><span data-stu-id="1d747-183">Migration guide</span></span>

<span data-ttu-id="1d747-184">Переход с веб-форм ASP.NET и универсальных поставщиков на ASP.NET Core удостоверение требует выполнения нескольких действий:</span><span class="sxs-lookup"><span data-stu-id="1d747-184">Migrating from ASP.NET Web Forms and universal providers to ASP.NET Core Identity requires several steps:</span></span>

1. <span data-ttu-id="1d747-185">Создание схемы базы данных удостоверений ASP.NET Core в целевой базе данных</span><span class="sxs-lookup"><span data-stu-id="1d747-185">Create ASP.NET Core Identity database schema in destination database</span></span>
2. <span data-ttu-id="1d747-186">Перенос данных из схемы универсального поставщика в ASP.NET Core схему удостоверений</span><span class="sxs-lookup"><span data-stu-id="1d747-186">Migrate data from universal provider schema to ASP.NET Core Identity schema</span></span>
3. <span data-ttu-id="1d747-187">Перенос конфигурации из web.config в промежуточное по и службы, обычно в `Startup.cs`</span><span class="sxs-lookup"><span data-stu-id="1d747-187">Migrate configuration from web.config to middleware and services, typically in `Startup.cs`</span></span>
4. <span data-ttu-id="1d747-188">Обновление отдельных страниц с помощью элементов управления и условных обозначений для использования вспомогательных функций тегов и новых интерфейсов API идентификации.</span><span class="sxs-lookup"><span data-stu-id="1d747-188">Update individual pages using controls and conditionals to use tag helpers and new identity APIs.</span></span>

<span data-ttu-id="1d747-189">В следующих разделах каждый этап рассматривается более подробно.</span><span class="sxs-lookup"><span data-stu-id="1d747-189">Each of these steps is described in detail in the following sections.</span></span>

### <a name="creating-the-aspnet-core-identity-schema"></a><span data-ttu-id="1d747-190">Создание схемы удостоверений ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1d747-190">Creating the ASP.NET Core Identity schema</span></span>

<span data-ttu-id="1d747-191">Существует несколько способов создания необходимой табличной структуры, используемой для ASP.NET Core удостоверения.</span><span class="sxs-lookup"><span data-stu-id="1d747-191">There are several ways to create the necessary table structure used for ASP.NET Core Identity.</span></span> <span data-ttu-id="1d747-192">Проще всего создать новое веб-приложение ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1d747-192">The simplest is to create a new ASP.NET Core Web application.</span></span> <span data-ttu-id="1d747-193">Выберите веб-приложение, а затем измените проверку подлинности, чтобы использовать учетные записи отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="1d747-193">Choose Web Application and then change Authentication to use Individual User Accounts.</span></span>

![новый проект с учетными записями отдельных пользователей](./media/security/individual-user-accounts.png)

<span data-ttu-id="1d747-195">В командной строке можно сделать то же самое, выполнив команду `dotnet new webapp -au Individual` .</span><span class="sxs-lookup"><span data-stu-id="1d747-195">From the command line, you can do the same thing by running `dotnet new webapp -au Individual`.</span></span> <span data-ttu-id="1d747-196">После создания приложения запустите его и зарегистрируйтесь на сайте.</span><span class="sxs-lookup"><span data-stu-id="1d747-196">Once the app has been created, run it and register on the site.</span></span> <span data-ttu-id="1d747-197">Следует активировать страницу, подобную показанной ниже:</span><span class="sxs-lookup"><span data-stu-id="1d747-197">You should trigger a page like the one shown below:</span></span>

![страница «применение миграций»](./media/security/apply-migrations-page.png)

<span data-ttu-id="1d747-199">Нажмите кнопку "применить миграции" и необходимо создать необходимые таблицы базы данных.</span><span class="sxs-lookup"><span data-stu-id="1d747-199">Click on the "Apply Migrations" button and the necessary database tables should be created for you.</span></span> <span data-ttu-id="1d747-200">Кроме того, файлы миграции должны отображаться в проекте, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="1d747-200">In addition, the migration files should appear in your project, as shown:</span></span>

![файлы миграции](./media/security/migration-files.png)

<span data-ttu-id="1d747-202">Вы можете запустить миграцию самостоятельно, не запуская веб-приложение, с помощью этого средства командной строки:</span><span class="sxs-lookup"><span data-stu-id="1d747-202">You can run the migration yourself, without running the web application, using this command line tool:</span></span>

```powershell
dotnet ef database update
```

<span data-ttu-id="1d747-203">Если вы предпочитаете использовать сценарий для применения новой схемы к существующей базе данных, можно создать скрипты для этих миграций из командной строки.</span><span class="sxs-lookup"><span data-stu-id="1d747-203">If you would rather run a script to apply the new schema to an existing database, you can script these migrations from the command line.</span></span> <span data-ttu-id="1d747-204">Выполните следующую команду, чтобы создать скрипт:</span><span class="sxs-lookup"><span data-stu-id="1d747-204">Run this command to generate the script:</span></span>

```powershell
dotnet ef migrations script -o auth.sql
```

<span data-ttu-id="1d747-205">Это приведет к созданию скрипта SQL в выходном файле `auth.sql` , который затем может выполняться в любой базе данных.</span><span class="sxs-lookup"><span data-stu-id="1d747-205">This will produce a SQL script in the output file `auth.sql` which can then be run against whatever database you like.</span></span> <span data-ttu-id="1d747-206">При возникновении проблем с выполнением `dotnet ef` команд [Убедитесь, что на компьютере установлены средства EF Core](https://docs.microsoft.com/ef/core/miscellaneous/cli/dotnet).</span><span class="sxs-lookup"><span data-stu-id="1d747-206">If you have any trouble running `dotnet ef` commands, [make sure you have the EF Core tools installed on your system](https://docs.microsoft.com/ef/core/miscellaneous/cli/dotnet).</span></span>

<span data-ttu-id="1d747-207">В случае, если у вас есть дополнительные столбцы в исходных таблицах, необходимо будет найти оптимальное расположение для этих столбцов в новой схеме.</span><span class="sxs-lookup"><span data-stu-id="1d747-207">In the event you have additional columns on your source tables, you will need to identify the best location for these columns in the new schema.</span></span> <span data-ttu-id="1d747-208">Как правило, столбцы, найденные в `aspnet_Membership` таблице, должны быть сопоставлены с `AspNetUsers` таблицей.</span><span class="sxs-lookup"><span data-stu-id="1d747-208">Generally, columns found on the `aspnet_Membership` table should be mapped to the `AspNetUsers` table.</span></span> <span data-ttu-id="1d747-209">Столбцы в `aspnet_Roles` должны быть сопоставлены с `AspNetRoles` .</span><span class="sxs-lookup"><span data-stu-id="1d747-209">Columns on `aspnet_Roles` should be mapped to `AspNetRoles`.</span></span> <span data-ttu-id="1d747-210">Все дополнительные столбцы таблицы будут `aspnet_UsersInRoles` добавлены в `AspNetUserRoles` таблицу.</span><span class="sxs-lookup"><span data-stu-id="1d747-210">Any additional columns on the `aspnet_UsersInRoles` table would be added to the `AspNetUserRoles` table.</span></span>

<span data-ttu-id="1d747-211">Также стоит рассмотреть возможность размещения дополнительных столбцов в отдельных таблицах, чтобы будущие миграции не могли учитывать такие настройки схемы удостоверений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1d747-211">It's also worth considering putting any additional columns on separate tables, so that future migrations won't need to take into account such customizations of the default identity schema.</span></span>

### <a name="migrating-data-from-universal-providers-to-aspnet-core-identity"></a><span data-ttu-id="1d747-212">Перенос данных от универсальных поставщиков в ASP.NET Core удостоверение</span><span class="sxs-lookup"><span data-stu-id="1d747-212">Migrating data from universal providers to ASP.NET Core Identity</span></span>

<span data-ttu-id="1d747-213">После создания схемы целевой таблицы необходимо перенести записи пользователя и роли в новую схему.</span><span class="sxs-lookup"><span data-stu-id="1d747-213">Once you have the destination table schema in place, the next step is to migrate your user and role records to the new schema.</span></span> <span data-ttu-id="1d747-214">Полный список различий схем, включая столбцы, сопоставленные с новыми столбцами, можно найти [здесь](https://docs.microsoft.com/aspnet/core/migration/proper-to-2x/membership-to-core-identity).</span><span class="sxs-lookup"><span data-stu-id="1d747-214">A complete list of the schema differences, including which columns map to which new columns, can be found [here](https://docs.microsoft.com/aspnet/core/migration/proper-to-2x/membership-to-core-identity).</span></span>

<span data-ttu-id="1d747-215">Чтобы перенести пользователей из группы в новые таблицы удостоверений, [выполните действия, описанные в документации](https://docs.microsoft.com/aspnet/core/migration/proper-to-2x/membership-to-core-identity).</span><span class="sxs-lookup"><span data-stu-id="1d747-215">To migrate your users from membership to the new identity tables, you should [follow the steps described in the documentation](https://docs.microsoft.com/aspnet/core/migration/proper-to-2x/membership-to-core-identity).</span></span> <span data-ttu-id="1d747-216">После выполнения этих действий и предоставленного скрипта пользователям потребуется изменить пароль при следующем входе в систему.</span><span class="sxs-lookup"><span data-stu-id="1d747-216">After following these steps and the script provided, your users will need to change their password the next time they log in.</span></span>

<span data-ttu-id="1d747-217">Можно выполнить миграцию паролей пользователей, но процесс является гораздо более сложным.</span><span class="sxs-lookup"><span data-stu-id="1d747-217">It is possible to migrate user passwords but the process is much more involved.</span></span> <span data-ttu-id="1d747-218">Требовать от пользователей обновления паролей в рамках процесса миграции и поощрение их использования новых, уникальных паролей, скорее всего, приведет к повышению общей безопасности приложения.</span><span class="sxs-lookup"><span data-stu-id="1d747-218">Requiring users to update their passwords as part of the migration process, and encouraging them to use new, unique passwords, is likely to enhance the overall security of the application.</span></span>

### <a name="migrating-security-settings-from-webconfig-to-startupcs"></a><span data-ttu-id="1d747-219">Перенос параметров безопасности из web.config в Startup.cs</span><span class="sxs-lookup"><span data-stu-id="1d747-219">Migrating security settings from web.config to Startup.cs</span></span>

<span data-ttu-id="1d747-220">Как отмечалось выше, поставщики членства и ролей ASP.NET настраиваются в файле web.config приложения.</span><span class="sxs-lookup"><span data-stu-id="1d747-220">As noted above, ASP.NET membership and role providers are configured in the application's web.config file.</span></span> <span data-ttu-id="1d747-221">Поскольку ASP.NET Core приложения не привязаны к службам IIS и используют отдельную систему для настройки, эти параметры должны быть настроены в другом расположении.</span><span class="sxs-lookup"><span data-stu-id="1d747-221">Since ASP.NET Core apps are not tied to IIS and use a separate system for configuration, these settings must be configured elsewhere.</span></span> <span data-ttu-id="1d747-222">В большинстве случаев ASP.NET Core удостоверение настраивается в `Startup.cs` файле.</span><span class="sxs-lookup"><span data-stu-id="1d747-222">For the most part, ASP.NET Core Identity is configured in the `Startup.cs` file.</span></span> <span data-ttu-id="1d747-223">Откройте созданный ранее веб-проект (чтобы создать схему таблицы удостоверений) и проверьте его `Startup.cs` файл.</span><span class="sxs-lookup"><span data-stu-id="1d747-223">Open the web project that was created earlier (to generate the identity table schema) and review its `Startup.cs` file.</span></span>

<span data-ttu-id="1d747-224">Метод ConfigureServices по умолчанию добавляет поддержку для EF Core и удостоверения.</span><span class="sxs-lookup"><span data-stu-id="1d747-224">The default ConfigureServices method adds support for EF Core and Identity:</span></span>

```csharp
// This method gets called by the runtime. Use this method to add services to the container.
public void ConfigureServices(IServiceCollection services)
{
    services.AddDbContext<ApplicationDbContext>(options =>
        options.UseSqlServer(
            Configuration.GetConnectionString("DefaultConnection")));

    services.AddDefaultIdentity<IdentityUser>(options => options.SignIn.RequireConfirmedAccount = true)
        .AddEntityFrameworkStores<ApplicationDbContext>();

    services.AddRazorPages();
}
```

<span data-ttu-id="1d747-225">`AddDefaultIdentity`Метод расширения используется для настройки удостоверения для использования значения по умолчанию `ApplicationDbContext` и `IdentityUser` типа платформы.</span><span class="sxs-lookup"><span data-stu-id="1d747-225">The `AddDefaultIdentity` extension method is used to configure Identity to use the default `ApplicationDbContext` and the framework's `IdentityUser` type.</span></span> <span data-ttu-id="1d747-226">Если вы используете настраиваемый объект `IdentityUser` , обязательно укажите его тип.</span><span class="sxs-lookup"><span data-stu-id="1d747-226">If you're using a custom `IdentityUser`, be sure to specify its type here.</span></span> <span data-ttu-id="1d747-227">Если эти методы расширения не работают в приложении, проверьте наличие соответствующих инструкций using и убедитесь, что у вас есть необходимые ссылки на пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="1d747-227">If these extension methods aren't working in your application, check that you have the appropriate using statements and that you have the necessary NuGet package references.</span></span> <span data-ttu-id="1d747-228">Например, в проекте должна быть установлена ссылка на несколько версий `Microsoft.AspNetCore.Identity.EntityFrameworkCore` `Microsoft.AspNetCore.Identity.UI` пакетов и.</span><span class="sxs-lookup"><span data-stu-id="1d747-228">For example, your project should have some version of the `Microsoft.AspNetCore.Identity.EntityFrameworkCore` and `Microsoft.AspNetCore.Identity.UI` packages referenced.</span></span>

<span data-ttu-id="1d747-229">Кроме того, в `Startup.cs` вы должны увидеть необходимое по промежуточного слоя, настроенное для сайта.</span><span class="sxs-lookup"><span data-stu-id="1d747-229">Also in `Startup.cs` you should see the necessary middleware configured for the site.</span></span> <span data-ttu-id="1d747-230">В частности, `UseAuthentication` и `UseAuthorization` должны быть настроены и в нужном месте.</span><span class="sxs-lookup"><span data-stu-id="1d747-230">Specifically, `UseAuthentication` and `UseAuthorization` should be set up, and in the proper location.</span></span>

```csharp

// This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
        app.UseDatabaseErrorPage();
    }
    else
    {
        app.UseExceptionHandler("/Error");
        // The default HSTS value is 30 days. You may want to change this for production scenarios, see https://aka.ms/aspnetcore-hsts.
        app.UseHsts();
    }

    app.UseHttpsRedirection();
    app.UseStaticFiles();

    app.UseRouting();

    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapRazorPages();
    });
}
```

<span data-ttu-id="1d747-231">ASP.NET Identity не настраивает анонимный или ролевой доступ к расположениям из `Startup.cs` .</span><span class="sxs-lookup"><span data-stu-id="1d747-231">ASP.NET Identity does not configure anonymous or role-based access to locations from `Startup.cs`.</span></span> <span data-ttu-id="1d747-232">Необходимо перенести данные конфигурации авторизации, зависящие от местоположения, в фильтры в ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1d747-232">You will need to migrate any location-specific authorization configuration data to filters in ASP.NET Core.</span></span> <span data-ttu-id="1d747-233">Запишите, какие папки и страницы потребует таких обновлений.</span><span class="sxs-lookup"><span data-stu-id="1d747-233">Make note of which folders and pages will require such updates.</span></span> <span data-ttu-id="1d747-234">Эти изменения будут внесены в следующий раздел.</span><span class="sxs-lookup"><span data-stu-id="1d747-234">You will make these changes in the next section.</span></span>

### <a name="updating-individual-pages-to-use-aspnet-core-identity-abstractions"></a><span data-ttu-id="1d747-235">Обновление отдельных страниц для использования абстракций ASP.NET Core удостоверений</span><span class="sxs-lookup"><span data-stu-id="1d747-235">Updating individual pages to use ASP.NET Core Identity abstractions</span></span>

<span data-ttu-id="1d747-236">В приложении ASP.NET Web Forms, если у вас есть web.config параметры для запрета доступа к определенным страницам или папкам анонимным пользователям, их необходимо перенести, просто добавив `[Authorize]` атрибут на такие страницы:</span><span class="sxs-lookup"><span data-stu-id="1d747-236">In your ASP.NET Web Forms application, if you had web.config settings to deny access to certain pages or folders to anonymous users, you would migrate these by simply adding the `[Authorize]` attribute to such pages:</span></span>

```razor
@attribute [Authorize]
```

<span data-ttu-id="1d747-237">Если доступ к другим пользователям был запрещен, за исключением тех, которые относятся к определенной роли, это также можно перенести, добавив атрибут, указывающий роль:</span><span class="sxs-lookup"><span data-stu-id="1d747-237">If you further had denied access except to those users belonging to a certain role, you would likewise migrate this by adding an attribute specifying a role:</span></span>

```razor
@attribute [Authorize(Roles ="administrators")]
```

<span data-ttu-id="1d747-238">Обратите внимание, что `[Authorize]` атрибут работает только для `@page` компонентов, достигнутых через Blazor маршрутизатор.</span><span class="sxs-lookup"><span data-stu-id="1d747-238">Note that the `[Authorize]` attribute only works on `@page` components that are reached via the Blazor Router.</span></span> <span data-ttu-id="1d747-239">Атрибут не работает с дочерними компонентами, которые вместо этого следует использовать `AuthorizeView` .</span><span class="sxs-lookup"><span data-stu-id="1d747-239">The attribute does not work with child components, which should instead use `AuthorizeView`.</span></span>

<span data-ttu-id="1d747-240">При наличии логики в разметке страницы для определения, следует ли отображать некоторый код для определенного пользователя, его можно заменить на `AuthorizeView` компонент.</span><span class="sxs-lookup"><span data-stu-id="1d747-240">If you have logic within page markup for determining whether to display some code to a certain user, you can replace this with the `AuthorizeView` component.</span></span> <span data-ttu-id="1d747-241">[Компонент аусоризевиев](https://docs.microsoft.com/aspnet/core/blazor/security#authorizeview-component) выборочно ОТОБРАЖАЕТ пользовательский интерфейс в зависимости от того, имеет ли пользователь разрешение на его просмотр.</span><span class="sxs-lookup"><span data-stu-id="1d747-241">The [AuthorizeView component](https://docs.microsoft.com/aspnet/core/blazor/security#authorizeview-component) selectively displays UI depending on whether the user is authorized to see it.</span></span> <span data-ttu-id="1d747-242">Он также предоставляет `context` переменную, которая может использоваться для доступа к сведениям о пользователе.</span><span class="sxs-lookup"><span data-stu-id="1d747-242">It also exposes a `context` variable that can be used to access user information.</span></span>

```razor
<AuthorizeView>
    <Authorized>
        <h1>Hello, @context.User.Identity.Name!</h1>
        <p>You can only see this content if you are authenticated.</p>
    </Authorized>
    <NotAuthorized>
        <h1>Authentication Failure!</h1>
        <p>You are not signed in.</p>
    </NotAuthorized>
</AuthorizeView>
```

<span data-ttu-id="1d747-243">Вы можете получить доступ к состоянию проверки подлинности в рамках процедурной логики, обратившись к пользователю из `Task<AuthenticationState` настроенного с помощью `[CascadingParameter]` атрибута.</span><span class="sxs-lookup"><span data-stu-id="1d747-243">You can access authentication state within procedural logic by accessing the user from a `Task<AuthenticationState` configured with the `[CascadingParameter]` attribute.</span></span> <span data-ttu-id="1d747-244">Это позволит получить доступ к пользователю, который позволит определить, прошли ли они проверку подлинности и принадлежат ли они определенной роли.</span><span class="sxs-lookup"><span data-stu-id="1d747-244">This will get you access to the user, which can let you determine if they are authenticated and if they belong to a particular role.</span></span> <span data-ttu-id="1d747-245">Если необходимо выполнить процедуру вычисления политики, можно внедрить экземпляр класса `IAuthorizationService` и вызвать `AuthorizeAsync` для него метод.</span><span class="sxs-lookup"><span data-stu-id="1d747-245">If you need to evaluate a policy procedurally, you can inject an instance of the `IAuthorizationService` and calls the `AuthorizeAsync` method on it.</span></span> <span data-ttu-id="1d747-246">В следующем примере кода показано, как получить сведения о пользователе и разрешить ему выполнять задачу, ограниченную `content-editor` политикой.</span><span class="sxs-lookup"><span data-stu-id="1d747-246">The following sample code demonstrates how to get user information and allow an authorized user to perform a task restricted by the `content-editor` policy.</span></span>

```razor
@using Microsoft.AspNetCore.Authorization
@inject IAuthorizationService AuthorizationService

<button @onclick="@DoSomething">Do something important</button>

@code {
    [CascadingParameter]
    private Task<AuthenticationState> authenticationStateTask { get; set; }

    private async Task DoSomething()
    {
        var user = (await authenticationStateTask).User;

        if (user.Identity.IsAuthenticated)
        {
            // Perform an action only available to authenticated (signed-in) users.
        }

        if (user.IsInRole("admin"))
        {
            // Perform an action only available to users in the 'admin' role.
        }

        if ((await AuthorizationService.AuthorizeAsync(user, "content-editor"))
            .Succeeded)
        {
            // Perform an action only available to users satisfying the
            // 'content-editor' policy.
        }
    }
}
```

<span data-ttu-id="1d747-247">`AuthenticationState`Прежде чем можно будет привязать к каскадному параметру, сначала необходимо настроить как каскадное значение.</span><span class="sxs-lookup"><span data-stu-id="1d747-247">The `AuthenticationState` does first need to be setup as a cascading value before it can be bound to a cascading parameter like this.</span></span> <span data-ttu-id="1d747-248">Обычно это делается с помощью `CascadingAuthenticationState` компонента.</span><span class="sxs-lookup"><span data-stu-id="1d747-248">That's typically done using the `CascadingAuthenticationState` component.</span></span> <span data-ttu-id="1d747-249">Обычно это делается в `App.razor` :</span><span class="sxs-lookup"><span data-stu-id="1d747-249">This is typically done in `App.razor`:</span></span>

```razor
<CascadingAuthenticationState>
    <Router AppAssembly="@typeof(Program).Assembly">
        <Found Context="routeData">
            <AuthorizeRouteView RouteData="@routeData"
                DefaultLayout="@typeof(MainLayout)" />
        </Found>
        <NotFound>
            <LayoutView Layout="@typeof(MainLayout)">
                <p>Sorry, there's nothing at this address.</p>
            </LayoutView>
        </NotFound>
    </Router>
</CascadingAuthenticationState>
```

## <a name="summary"></a><span data-ttu-id="1d747-250">Сводка</span><span class="sxs-lookup"><span data-stu-id="1d747-250">Summary</span></span>

<span data-ttu-id="1d747-251">Blazor использует ту же модель безопасности, что и ASP.NET Core, которая является ASP.NET Core удостоверением.</span><span class="sxs-lookup"><span data-stu-id="1d747-251">Blazor uses the same security model as ASP.NET Core, which is ASP.NET Core Identity.</span></span> <span data-ttu-id="1d747-252">Миграция с универсальных поставщиков на ASP.NET Core удостоверения относительно проста, предполагая, что к исходной схеме данных не применено слишком много настроек.</span><span class="sxs-lookup"><span data-stu-id="1d747-252">Migrating from universal providers to ASP.NET Core Identity is relatively straightforward, assuming not too much customization was applied to the original data schema.</span></span> <span data-ttu-id="1d747-253">После переноса данных работа с проверкой подлинности и авторизацией в Blazor приложениях хорошо документирована, с возможностью настройки и программной поддержки для большинства требований безопасности.</span><span class="sxs-lookup"><span data-stu-id="1d747-253">Once the data has been migrated, working with authentication and authorization in Blazor apps is well-documented, with configurable as well as programmatic support for most security requirements.</span></span>

## <a name="references"></a><span data-ttu-id="1d747-254">Ссылки</span><span class="sxs-lookup"><span data-stu-id="1d747-254">References</span></span>

- [<span data-ttu-id="1d747-255">Введение в удостоверение на ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1d747-255">Introduction to Identity on ASP.NET Core</span></span>](https://docs.microsoft.com/aspnet/core/security/authentication/identity)
- [<span data-ttu-id="1d747-256">Миграция с аутентификации членства ASP.NET на ASP.NET Core 2,0 удостоверение</span><span class="sxs-lookup"><span data-stu-id="1d747-256">Migrate from ASP.NET Membership authentication to ASP.NET Core 2.0 Identity</span></span>](https://docs.microsoft.com/aspnet/core/migration/proper-to-2x/membership-to-core-identity)
- [<span data-ttu-id="1d747-257">Перенесите проверку подлинности и удостоверение в ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1d747-257">Migrate Authentication and Identity to ASP.NET Core</span></span>](https://docs.microsoft.com/aspnet/core/migration/identity)
- [<span data-ttu-id="1d747-258">BlazorПроверка подлинности ASP.NET Core и авторизация</span><span class="sxs-lookup"><span data-stu-id="1d747-258">ASP.NET Core Blazor authentication and authorization</span></span>](https://docs.microsoft.com/aspnet/core/blazor/security/)

>[!div class="step-by-step"]
><span data-ttu-id="1d747-259">[Назад](config.md)
>[Вперед](migration.md)</span><span class="sxs-lookup"><span data-stu-id="1d747-259">[Previous](config.md)
[Next](migration.md)</span></span>
