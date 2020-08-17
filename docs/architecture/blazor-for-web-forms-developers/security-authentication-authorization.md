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
# <a name="security-authentication-and-authorization-in-aspnet-web-forms-and-no-locblazor"></a>Безопасность: проверка подлинности и авторизация в веб-формах ASP.NET и Blazor

Миграция из приложения веб-форм ASP.NET в Blazor почти наверняка требует обновления проверки подлинности и авторизации, предполагая, что для приложения настроена проверка подлинности. В этой главе рассматривается миграция из модели универсального поставщика веб-форм ASP.NET (для членства, ролей и профилей пользователей) и работа с удостоверениями ASP.NET Core из Blazor приложений. Хотя в этой главе рассматриваются основные этапы и рекомендации, подробные инструкции и сценарии можно найти в документации, на которую имеются ссылки.

## <a name="aspnet-universal-providers"></a>Универсальные поставщики ASP.NET

Начиная с ASP.NET 2,0 платформа веб-форм ASP.NET поддерживала модель поставщика для различных функций, включая членство. Поставщик универсального членства вместе с дополнительным поставщиком ролей очень часто развертывается с помощью приложений ASP.NET Web Forms. Он обеспечивает надежный и безопасный способ управления проверкой подлинности и авторизацией, которая будет работать уже сегодня. Последнее предложение этих универсальных поставщиков доступно в виде пакета NuGet, [Microsoft. AspNet. Providers](https://www.nuget.org/packages/Microsoft.AspNet.Providers).

Универсальные поставщики работать с схемой базы данных SQL, которая включает такие таблицы `aspnet_Applications` , как,, `aspnet_Membership` `aspnet_Roles` и `aspnet_Users` . При настройке с помощью [ командыaspnet_regsql.exe](https://docs.microsoft.com/previous-versions/ms229862(v=vs.140))поставщики устанавливают таблицы и хранимые процедуры, которые предоставляют все необходимые запросы и команды, необходимые для работы с базовыми данными. Схема базы данных и эти хранимые процедуры несовместимы с более новыми ASP.NET Identity и ASP.NET Core системами удостоверений, поэтому существующие данные должны быть перенесены в новую систему. На рис. 1 показан пример схемы таблицы, настроенной для универсальных поставщиков.

![Схема универсальных поставщиков](./media/security/membership-tables.png)

Универсальный поставщик обрабатывает пользователей, членство, роли и профили. Пользователям назначаются глобально уникальные идентификаторы и очень основные сведения (userId, userName) хранятся в `aspnet_Users` таблице. Сведения о проверке подлинности, такие как пароль, формат пароля, Salt пароля, счетчики блокировки и сведения и т. д., хранятся в `aspnet_Membership` таблице. Роли состоят только из имен и уникальных идентификаторов, которые назначаются пользователям через `aspnet_UsersInRoles` таблицу взаимосвязей, предоставляя связь «многие ко многим».

Если существующая система использует роли в дополнение к членству, необходимо перенести учетные записи пользователей, связанные пароли, роли и членство в роли в ASP.NET Core удостоверение. Вам также, скорее всего, потребуется обновить код, в котором выполняется проверка ролей с помощью инструкций If, вместо этого использовать декларативные фильтры, атрибуты и (или) вспомогательные функции тегов. В конце этой главы мы рассмотрим рекомендации по миграции более подробно.

### <a name="authorization-configuration-in-web-forms"></a>Настройка авторизации в веб-формах

Чтобы настроить Полномочный доступ к определенным страницам в приложении веб-форм ASP.NET, обычно вы указываете, что определенные страницы или папки недоступны для анонимных пользователей. Это делается в файле web.config:

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

В `authentication` разделе конфигурации настраивается проверка подлинности с помощью форм для приложения. `authorization`Раздел используется для запрета анонимных пользователей для всего приложения. Однако можно предоставить более детализированные правила авторизации для каждого расположения, а также применить проверки авторизации на основе ролей.

```xml
<location path="login.aspx">
  <system.web>
    <authorization>
      <allow users="*" />
    </authorization>
  </system.web>
</location>
```

Приведенная выше конфигурация при объединении с первой позволяет анонимным пользователям получать доступ к странице входа, переопределяя ограничение на уровне сайта для пользователей, не прошедших проверку подлинности.

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

Приведенная выше конфигурация, в сочетании с другими, позволяет ограничивать доступ к `/admin` папке и всем ее ресурсам членам роли "Администраторы". Это также можно применить, поместив отдельный `web.config` файл в `/admin` корневую папку.

### <a name="authorization-code-in-web-forms"></a>Код авторизации в веб-формах

Помимо настройки доступа с помощью `web.config` , можно также программно настроить доступ и поведение в приложении веб-форм. Например, можно ограничить возможность выполнения определенных операций или просмотра определенных данных в зависимости от роли пользователя.

Этот код можно использовать как в логике CodeBehind, так и на самой странице:

```html
<% if (HttpContext.Current.User.IsInRole("Administrators")) { %>
  <a href="/admin">Go To Admin</a>
<% } %>
```

Помимо проверки членства в роли пользователя, можно также определить, прошли ли они проверку подлинности (хотя часто это лучше выполнить с использованием конфигурации на основе расположения, описанной выше). Ниже приведен пример такого подхода.

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

В приведенном выше коде управление доступом на основе ролей (RBAC) используется для определения того, видимы ли определенные элементы страницы, например, в `SecretPanel` зависимости от роли текущего пользователя.

Как правило, приложения ASP.NET Web Forms настраивают безопасность в `web.config` файле, а затем добавляют дополнительные проверки, если это необходимо на `.aspx` страницах и связанных с ними `.aspx.cs` файлах кода поддержки. Большинство приложений используют универсального поставщика членства, часто с дополнительным поставщиком ролей.

## <a name="aspnet-core-identity"></a>Идентификация ASP.NET Core

Несмотря на то, что по-прежнему выполняется проверка подлинности и авторизация, ASP.NET Core удостоверение использует другой набор абстракций и допущений по сравнению с универсальными поставщиками. Например, Новая модель удостоверений поддерживает проверку подлинности третьих сторон, позволяя пользователям проходить проверку подлинности с помощью учетной записи социальных сетей или другого доверенного поставщика проверки подлинности. ASP.NET Core Identity поддерживает пользовательский интерфейс для часто необходимых страниц, таких как вход, выход и регистрация. Он использует EF Core для доступа к данным, а EF Core миграции для создания необходимой схемы, необходимой для поддержки ее модели данных. Это [Введение в идентификацию на ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/identity) предоставляет хороший обзор того, что входит в состав ASP.NET Core удостоверений и как приступить к работе с ним. Если вы еще не настроили удостоверение ASP.NET Core в приложении и его базе данных, оно поможет приступить к работе.

### <a name="roles-claims-and-policies"></a>Роли, утверждения и политики

Универсальные поставщики и удостоверение ASP.NET Core поддерживают концепцию ролей. Вы можете создавать роли для пользователей и назначать им роли. Пользователи могут принадлежать любому количеству ролей, и вы можете проверить членство в роли в рамках реализации авторизации.

Помимо ролей, ASP.NET Core Identity поддерживает концепции заявок и политик. Хотя роль должна соответствовать набору ресурсов, доступ к которым должен иметь пользователь этой роли, утверждение — это просто часть удостоверения пользователя. Утверждение — это пара "имя-значение", которая представляет предметную тему, а не то, что может делать субъект.

Можно напрямую проверить утверждения пользователя и определить, следует ли пользователю предоставлять доступ к ресурсу. Однако такие проверки часто повторяются и разбросаны по всей системе. Лучшим подходом является определение *политики*.

Политика авторизации состоит из одного или нескольких требований. Политики регистрируются как часть конфигурации службы авторизации в `ConfigureServices` методе `Startup.cs` . Например, следующий фрагмент кода настраивает политику с именем "Канадиансонли", которая требует, чтобы пользователь имел утверждение страны со значением "Канада".

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("CanadiansOnly", policy => policy.RequireClaim(ClaimTypes.Country, "Canada"));
});
```

[Дополнительные сведения о создании пользовательских политик см. в документации](https://docs.microsoft.com/aspnet/core/security/authorization/policies).

Независимо от того, используете ли вы политики или роли, вы можете указать, что конкретная страница в Blazor приложении должна иметь роль или политику с `[Authorize]` атрибутом, применяемую с `@attribute` директивой.

Требования к роли:

```csharp
@attribute [Authorize(Roles ="administrators")]
```

Требовать соблюдение политики:

```csharp
@attribute [Authorize(Policy ="CanadiansOnly")]
```

Если вам требуется доступ к состоянию проверки подлинности, ролям или утверждениям пользователя в коде, существует два основных способа добиться этого. Первый — получение состояния проверки подлинности в виде каскадного параметра. Второй — доступ к состоянию с помощью внедренного `AuthenticationStateProvider` . Сведения о каждом из этих подходов описаны в [ Blazor документации по безопасности](https://docs.microsoft.com/aspnet/core/blazor/security/).

В следующем коде показано, как получить в `AuthenticationState` качестве каскадного параметра:

```csharp
[CascadingParameter]
private Task<AuthenticationState> authenticationStateTask { get; set; }
```

С помощью этого параметра можно получить пользователя, используя следующий код:

```csharp
var authState = await authenticationStateTask;
var user = authState.User;
```

В следующем коде показано, как внедрить `AuthenticationStateProvider` :

```csharp
@using Microsoft.AspNetCore.Components.Authorization
@inject AuthenticationStateProvider AuthenticationStateProvider
```

Используя поставщик, вы можете получить доступ к пользователю с помощью следующего кода:

```csharp
AuthenticationState authState = await AuthenticationStateProvider.GetAuthenticationStateAsync();
ClaimsPrincipal user = authState.User;

if (user.Identity.IsAuthenticated)
{
  // work with user.Claims and/or user.Roles
}
```

**Примечание.** `AuthorizeView` Компонент, рассмотренный далее в этой главе, предоставляет декларативный способ управления тем, что видит пользователь на странице или в компоненте.

Для работы с пользователями и утверждениями (в Blazor серверных приложениях) также может потребоваться внедрить `UserManager<T>` (использовать `IdentityUser` для использования по умолчанию), который можно использовать для перечисления и изменения утверждений для пользователя. Сначала вставьте тип и присвойте его свойству:

```csharp
@inject UserManager<IdentityUser> MyUserManager
```

Затем используйте его для работы с утверждениями пользователя. В следующем примере показано, как добавить и сохранить утверждение для пользователя.

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

Если необходимо работать с ролями, используйте тот же подход. Может потребоваться внедрить `RoleManager<T>` (использовать `IdentityRole` для типа по умолчанию), чтобы перечислить сами роли и управлять ими.

**Примечание.** В Blazor проектах сборки для выполнения этих операций необходимо предоставить API-интерфейсы сервера (вместо использования `UserManager<T>` или `RoleManager<T>` непосредственно). BlazorКлиентское приложение сборки может управлять утверждениями и (или) ролями путем безопасного вызова конечных точек API, предоставляемых для этой цели.

### <a name="migration-guide"></a>Руководство по миграции

Переход с веб-форм ASP.NET и универсальных поставщиков на ASP.NET Core удостоверение требует выполнения нескольких действий:

1. Создание схемы базы данных удостоверений ASP.NET Core в целевой базе данных
2. Перенос данных из схемы универсального поставщика в ASP.NET Core схему удостоверений
3. Перенос конфигурации из web.config в промежуточное по и службы, обычно в `Startup.cs`
4. Обновление отдельных страниц с помощью элементов управления и условных обозначений для использования вспомогательных функций тегов и новых интерфейсов API идентификации.

В следующих разделах каждый этап рассматривается более подробно.

### <a name="creating-the-aspnet-core-identity-schema"></a>Создание схемы удостоверений ASP.NET Core

Существует несколько способов создания необходимой табличной структуры, используемой для ASP.NET Core удостоверения. Проще всего создать новое веб-приложение ASP.NET Core. Выберите веб-приложение, а затем измените проверку подлинности, чтобы использовать учетные записи отдельных пользователей.

![новый проект с учетными записями отдельных пользователей](./media/security/individual-user-accounts.png)

В командной строке можно сделать то же самое, выполнив команду `dotnet new webapp -au Individual` . После создания приложения запустите его и зарегистрируйтесь на сайте. Следует активировать страницу, подобную показанной ниже:

![страница «применение миграций»](./media/security/apply-migrations-page.png)

Нажмите кнопку "применить миграции" и необходимо создать необходимые таблицы базы данных. Кроме того, файлы миграции должны отображаться в проекте, как показано ниже.

![файлы миграции](./media/security/migration-files.png)

Вы можете запустить миграцию самостоятельно, не запуская веб-приложение, с помощью этого средства командной строки:

```powershell
dotnet ef database update
```

Если вы предпочитаете использовать сценарий для применения новой схемы к существующей базе данных, можно создать скрипты для этих миграций из командной строки. Выполните следующую команду, чтобы создать скрипт:

```powershell
dotnet ef migrations script -o auth.sql
```

Это приведет к созданию скрипта SQL в выходном файле `auth.sql` , который затем может выполняться в любой базе данных. При возникновении проблем с выполнением `dotnet ef` команд [Убедитесь, что на компьютере установлены средства EF Core](https://docs.microsoft.com/ef/core/miscellaneous/cli/dotnet).

В случае, если у вас есть дополнительные столбцы в исходных таблицах, необходимо будет найти оптимальное расположение для этих столбцов в новой схеме. Как правило, столбцы, найденные в `aspnet_Membership` таблице, должны быть сопоставлены с `AspNetUsers` таблицей. Столбцы в `aspnet_Roles` должны быть сопоставлены с `AspNetRoles` . Все дополнительные столбцы таблицы будут `aspnet_UsersInRoles` добавлены в `AspNetUserRoles` таблицу.

Также стоит рассмотреть возможность размещения дополнительных столбцов в отдельных таблицах, чтобы будущие миграции не могли учитывать такие настройки схемы удостоверений по умолчанию.

### <a name="migrating-data-from-universal-providers-to-aspnet-core-identity"></a>Перенос данных от универсальных поставщиков в ASP.NET Core удостоверение

После создания схемы целевой таблицы необходимо перенести записи пользователя и роли в новую схему. Полный список различий схем, включая столбцы, сопоставленные с новыми столбцами, можно найти [здесь](https://docs.microsoft.com/aspnet/core/migration/proper-to-2x/membership-to-core-identity).

Чтобы перенести пользователей из группы в новые таблицы удостоверений, [выполните действия, описанные в документации](https://docs.microsoft.com/aspnet/core/migration/proper-to-2x/membership-to-core-identity). После выполнения этих действий и предоставленного скрипта пользователям потребуется изменить пароль при следующем входе в систему.

Можно выполнить миграцию паролей пользователей, но процесс является гораздо более сложным. Требовать от пользователей обновления паролей в рамках процесса миграции и поощрение их использования новых, уникальных паролей, скорее всего, приведет к повышению общей безопасности приложения.

### <a name="migrating-security-settings-from-webconfig-to-startupcs"></a>Перенос параметров безопасности из web.config в Startup.cs

Как отмечалось выше, поставщики членства и ролей ASP.NET настраиваются в файле web.config приложения. Поскольку ASP.NET Core приложения не привязаны к службам IIS и используют отдельную систему для настройки, эти параметры должны быть настроены в другом расположении. В большинстве случаев ASP.NET Core удостоверение настраивается в `Startup.cs` файле. Откройте созданный ранее веб-проект (чтобы создать схему таблицы удостоверений) и проверьте его `Startup.cs` файл.

Метод ConfigureServices по умолчанию добавляет поддержку для EF Core и удостоверения.

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

`AddDefaultIdentity`Метод расширения используется для настройки удостоверения для использования значения по умолчанию `ApplicationDbContext` и `IdentityUser` типа платформы. Если вы используете настраиваемый объект `IdentityUser` , обязательно укажите его тип. Если эти методы расширения не работают в приложении, проверьте наличие соответствующих инструкций using и убедитесь, что у вас есть необходимые ссылки на пакет NuGet. Например, в проекте должна быть установлена ссылка на несколько версий `Microsoft.AspNetCore.Identity.EntityFrameworkCore` `Microsoft.AspNetCore.Identity.UI` пакетов и.

Кроме того, в `Startup.cs` вы должны увидеть необходимое по промежуточного слоя, настроенное для сайта. В частности, `UseAuthentication` и `UseAuthorization` должны быть настроены и в нужном месте.

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

ASP.NET Identity не настраивает анонимный или ролевой доступ к расположениям из `Startup.cs` . Необходимо перенести данные конфигурации авторизации, зависящие от местоположения, в фильтры в ASP.NET Core. Запишите, какие папки и страницы потребует таких обновлений. Эти изменения будут внесены в следующий раздел.

### <a name="updating-individual-pages-to-use-aspnet-core-identity-abstractions"></a>Обновление отдельных страниц для использования абстракций ASP.NET Core удостоверений

В приложении ASP.NET Web Forms, если у вас есть web.config параметры для запрета доступа к определенным страницам или папкам анонимным пользователям, их необходимо перенести, просто добавив `[Authorize]` атрибут на такие страницы:

```razor
@attribute [Authorize]
```

Если доступ к другим пользователям был запрещен, за исключением тех, которые относятся к определенной роли, это также можно перенести, добавив атрибут, указывающий роль:

```razor
@attribute [Authorize(Roles ="administrators")]
```

Обратите внимание, что `[Authorize]` атрибут работает только для `@page` компонентов, достигнутых через Blazor маршрутизатор. Атрибут не работает с дочерними компонентами, которые вместо этого следует использовать `AuthorizeView` .

При наличии логики в разметке страницы для определения, следует ли отображать некоторый код для определенного пользователя, его можно заменить на `AuthorizeView` компонент. [Компонент аусоризевиев](https://docs.microsoft.com/aspnet/core/blazor/security#authorizeview-component) выборочно ОТОБРАЖАЕТ пользовательский интерфейс в зависимости от того, имеет ли пользователь разрешение на его просмотр. Он также предоставляет `context` переменную, которая может использоваться для доступа к сведениям о пользователе.

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

Вы можете получить доступ к состоянию проверки подлинности в рамках процедурной логики, обратившись к пользователю из `Task<AuthenticationState` настроенного с помощью `[CascadingParameter]` атрибута. Это позволит получить доступ к пользователю, который позволит определить, прошли ли они проверку подлинности и принадлежат ли они определенной роли. Если необходимо выполнить процедуру вычисления политики, можно внедрить экземпляр класса `IAuthorizationService` и вызвать `AuthorizeAsync` для него метод. В следующем примере кода показано, как получить сведения о пользователе и разрешить ему выполнять задачу, ограниченную `content-editor` политикой.

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

`AuthenticationState`Прежде чем можно будет привязать к каскадному параметру, сначала необходимо настроить как каскадное значение. Обычно это делается с помощью `CascadingAuthenticationState` компонента. Обычно это делается в `App.razor` :

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

## <a name="summary"></a>Сводка

Blazor использует ту же модель безопасности, что и ASP.NET Core, которая является ASP.NET Core удостоверением. Миграция с универсальных поставщиков на ASP.NET Core удостоверения относительно проста, предполагая, что к исходной схеме данных не применено слишком много настроек. После переноса данных работа с проверкой подлинности и авторизацией в Blazor приложениях хорошо документирована, с возможностью настройки и программной поддержки для большинства требований безопасности.

## <a name="references"></a>Ссылки

- [Введение в удостоверение на ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/identity)
- [Миграция с аутентификации членства ASP.NET на ASP.NET Core 2,0 удостоверение](https://docs.microsoft.com/aspnet/core/migration/proper-to-2x/membership-to-core-identity)
- [Перенесите проверку подлинности и удостоверение в ASP.NET Core](https://docs.microsoft.com/aspnet/core/migration/identity)
- [BlazorПроверка подлинности ASP.NET Core и авторизация](https://docs.microsoft.com/aspnet/core/blazor/security/)

>[!div class="step-by-step"]
>[Назад](config.md)
>[Вперед](migration.md)
