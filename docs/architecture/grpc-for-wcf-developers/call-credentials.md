---
title: Вызов учетных данных — gRPC для разработчиков WCF
description: Как реализовать и использовать учетные данные вызова gRPC в ASP.NET Core 3,0.
ms.date: 12/15/2020
ms.openlocfilehash: 66394c75929bf068f83d631e022b467386e59ec5
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938446"
---
# <a name="call-credentials"></a>Учетные данные вызова

Учетные данные вызова основаны на маркере, переданном в метаданных с каждым запросом.

## <a name="ws-federation"></a>WS-Federation

ASP.NET Core поддерживает WS-Federation с помощью пакета NuGet [WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) . WS-Federation является ближайшей доступной альтернативой проверки подлинности Windows, которая не поддерживается по протоколу HTTP/2. Проверка подлинности пользователей осуществляется с помощью службы федерации Active Directory (AD FS) (AD FS), который предоставляет маркер, который можно использовать для проверки подлинности с помощью ASP.NET Core.

Дополнительные сведения о том, как приступить к работе с этим методом проверки подлинности, см. [в разделе Проверка подлинности пользователей с WS-Federation в ASP.NET Core](/aspnet/core/security/authentication/ws-federation).

## <a name="jwt-bearer-tokens"></a>Токены носителя JWT

Стандарт [JSON Web Token](https://jwt.io) (JWT) предоставляет способ кодирования сведений о пользователе и их утверждениях в закодированной строке. Он также предоставляет способ подписи маркера, чтобы потребитель мог проверить целостность маркера с помощью шифрования с открытым ключом. Можно использовать различные службы, например IdentityServer4, для проверки подлинности пользователей и создания маркеров OpenID Connect Connect (OIDC) для использования с gRPC и API HTTP.

ASP.NET Core 5,0 может работать с JWT с помощью пакета носителя JWT. Конфигурация одинакова для приложения gRPC, так же как для приложения ASP.NET Core MVC. Здесь мы рассмотрим токены носителя JWT, так как их проще разрабатывать, чем WS-Federation.

## <a name="add-authentication-and-authorization-to-the-server"></a>Добавление проверки подлинности и авторизации на сервер

Пакет носителя JWT не входит в ASP.NET Core 5,0 по умолчанию. Установите пакет NuGet [Microsoft. AspNetCore. Authentication. JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) в приложении.

Добавьте службу проверки подлинности в класс Startup и настройте обработчик носителя JWT:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();

    var signingKey = ObtainSigningKeySomehow();

    services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
        .AddJwtBearer(options =>
        {
            options.TokenValidationParameters =
                new TokenValidationParameters
                {
                    ValidateAudience = false,
                    ValidateIssuer = false,
                    ValidateActor = false,
                    ValidateLifetime = true,
                    IssuerSigningKey = signingKey
                };
        });

}
```

`IssuerSigningKey`Для этого свойства требуется реализация `Microsoft.IdentityModels.Tokens.SecurityKey` с использованием криптографических данных, необходимых для проверки подписанных токенов. Безопасно Храните этот маркер на *сервере секретов*, например Azure Key Vault.

Затем добавьте службу авторизации, которая управляет доступом к системе:

```csharp
    services.AddAuthorization(options =>
    {
        options.AddPolicy(JwtBearerDefaults.AuthenticationScheme, policy =>
        {
            policy.AddAuthenticationSchemes(JwtBearerDefaults.AuthenticationScheme);
            policy.RequireClaim(ClaimTypes.Name);
        });
    });

```

> [!TIP]
> Проверка подлинности и авторизация — это два отдельных шага. Для определения удостоверения пользователя используется проверка подлинности. С помощью авторизации можно определить, разрешено ли этому пользователю доступ к различным частям системы.

Теперь добавьте по промежуточного слоя проверки подлинности и авторизации в ASP.NET Core конвейер в `Configure` методе:

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    // Authenticate, then Authorize
    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

Наконец, примените `[Authorize]` атрибут к любым службам или методам, которые необходимо защитить, и используйте `User` свойство из базового `HttpContext` для проверки разрешений.

```csharp
[Authorize]
public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!TryValidateUser(request.TraderId, context.GetHttpContext().User))
    {
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Denied."));
    }

    var portfolio = await _repository.GetAsync(traderId, request.PortfolioId);

    return new GetResponse
    {
        Portfolio = Portfolio.FromRepositoryModel(portfolio)
    };
}
```

## <a name="provide-call-credentials-in-the-client-application"></a>Предоставление учетных данных вызова в клиентском приложении

После получения маркера JWT с сервера удостоверений его можно использовать для проверки подлинности вызовов gRPC из клиента, добавив его в качестве заголовка метаданных в вызове следующим образом:

```csharp
public async Task ShowPortfolioAsync(int portfolioId)
{
    var headers = new Grpc.Core.Metadata
    {
        { "Authorization", $"Bearer {_userToken}" }
    };
    var request = new GetRequest
    {
        TraderId = _userId,
        PortfolioId = portfolioId
    };
    var response = await _portfoliosClient.GetAsync(request, headers);

    // Display portfolio
}
```

Теперь вы защитили службу gRPC с помощью токенов носителя JWT в качестве учетных данных вызова. В GitHub будет [добавлена версия примера gRPC приложения с проверкой подлинности и авторизацией](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) .

>[!div class="step-by-step"]
>[Назад](security.md)
>[Вперед](channel-credentials.md)
