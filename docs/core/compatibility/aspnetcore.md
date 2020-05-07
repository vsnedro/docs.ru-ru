---
title: Критические изменения ASP.NET Core
titleSuffix: ''
description: В этой статье приведен список критических изменений в ASP.NET Core.
ms.date: 04/29/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: 63d39b1aa6e46b6bcbeb5a409efacac01dea4262
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728342"
---
# <a name="aspnet-core-breaking-changes"></a><span data-ttu-id="beb82-103">Критические изменения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="beb82-103">ASP.NET Core breaking changes</span></span>

<span data-ttu-id="beb82-104">ASP.NET Core предоставляет функции разработки веб-приложений, используемые .NET Core.</span><span class="sxs-lookup"><span data-stu-id="beb82-104">ASP.NET Core provides the web app development features used by .NET Core.</span></span>

<span data-ttu-id="beb82-105">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="beb82-105">The following breaking changes are documented on this page:</span></span>

- [<span data-ttu-id="beb82-106">Удалены устаревшие API в областях борьбы с фальсификацией, CORS, диагностики, MVC и маршрутизации</span><span class="sxs-lookup"><span data-stu-id="beb82-106">Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed</span></span>](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [<span data-ttu-id="beb82-107">Проверка подлинности. Использование Google + прекращено</span><span class="sxs-lookup"><span data-stu-id="beb82-107">Authentication: Google+ deprecation</span></span>](#authentication-google-deprecated-and-replaced)
- [<span data-ttu-id="beb82-108">Проверка подлинности. Удалено свойство HttpContext.Authentication</span><span class="sxs-lookup"><span data-stu-id="beb82-108">Authentication: HttpContext.Authentication property removed</span></span>](#authentication-httpcontextauthentication-property-removed)
- [<span data-ttu-id="beb82-109">Проверка подлинности. Заменены типы Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="beb82-109">Authentication: Newtonsoft.Json types replaced</span></span>](#authentication-newtonsoftjson-types-replaced)
- [<span data-ttu-id="beb82-110">Проверка подлинности. Изменена подпись ExchangeCodeAsync OAuthHandler</span><span class="sxs-lookup"><span data-stu-id="beb82-110">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [<span data-ttu-id="beb82-111">Авторизация. Перегрузка AddAuthorization перемещена в другую сборку</span><span class="sxs-lookup"><span data-stu-id="beb82-111">Authorization: AddAuthorization overload moved to different assembly</span></span>](#authorization-addauthorization-overload-moved-to-different-assembly)
- [<span data-ttu-id="beb82-112">Авторизация. IAllowAnonymous удален из AuthorizationFilterContext.Filters</span><span class="sxs-lookup"><span data-stu-id="beb82-112">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [<span data-ttu-id="beb82-113">Авторизация. Для реализаций IAuthorizationPolicyProvider требуется новый метод</span><span class="sxs-lookup"><span data-stu-id="beb82-113">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [<span data-ttu-id="beb82-114">Общие сведения Пакеты интеграции Azure с префиксом Майкрософт удалены</span><span class="sxs-lookup"><span data-stu-id="beb82-114">Azure: Microsoft-prefixed Azure integration packages removed</span></span>](#azure-microsoft-prefixed-azure-integration-packages-removed)
- [<span data-ttu-id="beb82-115">Кэширование. Удалено свойство CompactOnMemoryPressure</span><span class="sxs-lookup"><span data-stu-id="beb82-115">Caching: CompactOnMemoryPressure property removed</span></span>](#caching-compactonmemorypressure-property-removed)
- [<span data-ttu-id="beb82-116">Кэширование. Microsoft.Extensions.Caching.SqlServer использует новый пакет SqlClient</span><span class="sxs-lookup"><span data-stu-id="beb82-116">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [<span data-ttu-id="beb82-117">Кэширование. Типы ResponseCaching pubternal теперь стали внутренними</span><span class="sxs-lookup"><span data-stu-id="beb82-117">Caching: ResponseCaching "pubternal" types changed to internal</span></span>](#caching-responsecaching-pubternal-types-changed-to-internal)
- [<span data-ttu-id="beb82-118">Защита данных. DataProtection.AzureStorage использует новые API службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="beb82-118">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [<span data-ttu-id="beb82-119">Расширения. Изменения ссылок на пакеты, затрагивающие некоторые пакеты NuGet</span><span class="sxs-lookup"><span data-stu-id="beb82-119">Extensions: Package reference changes affecting some NuGet packages</span></span>](#extensions-package-reference-changes-affecting-some-nuget-packages)
- [<span data-ttu-id="beb82-120">Размещение. Модуль AspNetCoreModule версии 1 удален из пакета размещения Windows</span><span class="sxs-lookup"><span data-stu-id="beb82-120">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [<span data-ttu-id="beb82-121">Размещение. Универсальный узел ограничивает внедрение через конструктор Startup</span><span class="sxs-lookup"><span data-stu-id="beb82-121">Hosting: Generic host restricts Startup constructor injection</span></span>](#hosting-generic-host-restricts-startup-constructor-injection)
- [<span data-ttu-id="beb82-122">Размещение. Для приложений IIS вне процесса включено перенаправление HTTPS</span><span class="sxs-lookup"><span data-stu-id="beb82-122">Hosting: HTTPS redirection enabled for IIS out-of-process apps</span></span>](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [<span data-ttu-id="beb82-123">Размещение. Удалены типы IHostingEnvironment и IApplicationLifetime</span><span class="sxs-lookup"><span data-stu-id="beb82-123">Hosting: IHostingEnvironment and IApplicationLifetime types replaced</span></span>](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="beb82-124">Размещение. ObjectPoolProvider удален из зависимостей WebHostBuilder</span><span class="sxs-lookup"><span data-stu-id="beb82-124">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [<span data-ttu-id="beb82-125">HTTP. Типы Kestrel и IIS BadHttpRequestException, помеченные как устаревшие и замененные</span><span class="sxs-lookup"><span data-stu-id="beb82-125">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>](#http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="beb82-126">HTTP. Изменения SameSite в браузере влияют на проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="beb82-126">HTTP: Browser SameSite changes impact authentication</span></span>](#http-browser-samesite-changes-impact-authentication)
- [<span data-ttu-id="beb82-127">HTTP. Удалена расширяемость DefaultHttpContext</span><span class="sxs-lookup"><span data-stu-id="beb82-127">HTTP: DefaultHttpContext extensibility removed</span></span>](#http-defaulthttpcontext-extensibility-removed)
- [<span data-ttu-id="beb82-128">HTTP. Поля HeaderNames изменены на статические только для чтения</span><span class="sxs-lookup"><span data-stu-id="beb82-128">HTTP: HeaderNames fields changed to static readonly</span></span>](#http-headernames-constants-changed-to-static-readonly)
- [<span data-ttu-id="beb82-129">HTTP. Экземпляры HttpClient, созданные с помощью целочисленных кодов состояния журнала IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="beb82-129">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>](#http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes)
- [<span data-ttu-id="beb82-130">HTTP. Изменения в инфраструктуре текста ответа</span><span class="sxs-lookup"><span data-stu-id="beb82-130">HTTP: Response body infrastructure changes</span></span>](#http-response-body-infrastructure-changes)
- [<span data-ttu-id="beb82-131">HTTP. Внесены изменения в некоторые значения по умолчанию для параметра SameSite для файлов cookie</span><span class="sxs-lookup"><span data-stu-id="beb82-131">HTTP: Some cookie SameSite default values changed</span></span>](#http-some-cookie-samesite-defaults-changed-to-none)
- [<span data-ttu-id="beb82-132">HTTP. Синхронный ввод-вывода отключен по умолчанию</span><span class="sxs-lookup"><span data-stu-id="beb82-132">HTTP: Synchronous IO disabled by default</span></span>](#http-synchronous-io-disabled-in-all-servers)
- [<span data-ttu-id="beb82-133">Удостоверение. Удалена перегрузка метода AddDefaultUI</span><span class="sxs-lookup"><span data-stu-id="beb82-133">Identity: AddDefaultUI method overload removed</span></span>](#identity-adddefaultui-method-overload-removed)
- [<span data-ttu-id="beb82-134">Удостоверение. Изменена версия начальной загрузки пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="beb82-134">Identity: UI Bootstrap version change</span></span>](#identity-default-bootstrap-version-of-ui-changed)
- [<span data-ttu-id="beb82-135">Удостоверение. SignInAsync создает исключение для удостоверения, не прошедшего проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="beb82-135">Identity: SignInAsync throws exception for unauthenticated identity</span></span>](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [<span data-ttu-id="beb82-136">Удостоверение. Конструктор SignInManager принимает новый параметр</span><span class="sxs-lookup"><span data-stu-id="beb82-136">Identity: SignInManager constructor accepts new parameter</span></span>](#identity-signinmanager-constructor-accepts-new-parameter)
- [<span data-ttu-id="beb82-137">Удостоверение. Пользовательский интерфейс использует функцию статических веб-ресурсов</span><span class="sxs-lookup"><span data-stu-id="beb82-137">Identity: UI uses static web assets feature</span></span>](#identity-ui-uses-static-web-assets-feature)
- [<span data-ttu-id="beb82-138">Kestrel. Удалены адаптеры подключений</span><span class="sxs-lookup"><span data-stu-id="beb82-138">Kestrel: Connection adapters removed</span></span>](#kestrel-connection-adapters-removed)
- [<span data-ttu-id="beb82-139">Kestrel. Удалена пустая сборка HTTPS</span><span class="sxs-lookup"><span data-stu-id="beb82-139">Kestrel: Empty HTTPS assembly removed</span></span>](#kestrel-empty-https-assembly-removed)
- [<span data-ttu-id="beb82-140">Kestrel. Заголовки трейлеров запросов перемещены в новую коллекцию</span><span class="sxs-lookup"><span data-stu-id="beb82-140">Kestrel: Request trailer headers moved to new collection</span></span>](#kestrel-request-trailer-headers-moved-to-new-collection)
- [<span data-ttu-id="beb82-141">Kestrel. Внесены изменения в слой абстракции транспорта</span><span class="sxs-lookup"><span data-stu-id="beb82-141">Kestrel: Transport abstraction layer changes</span></span>](#kestrel-transport-abstractions-removed-and-made-public)
- [<span data-ttu-id="beb82-142">Локализация. Интерфейсы API отмечены как устаревшие</span><span class="sxs-lookup"><span data-stu-id="beb82-142">Localization: APIs marked obsolete</span></span>](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [<span data-ttu-id="beb82-143">Локализация. Удален класс ResourceManagerWithCultureStringLocalizer и элемент интерфейса WithCulture</span><span class="sxs-lookup"><span data-stu-id="beb82-143">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>](#localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed)
- [<span data-ttu-id="beb82-144">Ведение журнала. Класс DebugLogger стал внутренним</span><span class="sxs-lookup"><span data-stu-id="beb82-144">Logging: DebugLogger class made internal</span></span>](#logging-debuglogger-class-made-internal)
- [<span data-ttu-id="beb82-145">MVC. Удален асинхронный суффикс действия контроллера</span><span class="sxs-lookup"><span data-stu-id="beb82-145">MVC: Controller action Async suffix removed</span></span>](#mvc-async-suffix-trimmed-from-controller-action-names)
- [<span data-ttu-id="beb82-146">MVC. JsonResult перемещен в Microsoft.AspNetCore.Mvc.Core</span><span class="sxs-lookup"><span data-stu-id="beb82-146">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [<span data-ttu-id="beb82-147">MVC. Использование средства предварительной компиляции прекращено</span><span class="sxs-lookup"><span data-stu-id="beb82-147">MVC: Precompilation tool deprecated</span></span>](#mvc-precompilation-tool-deprecated)
- [<span data-ttu-id="beb82-148">MVC. Типы теперь стали внутренними</span><span class="sxs-lookup"><span data-stu-id="beb82-148">MVC: Types changed to internal</span></span>](#mvc-pubternal-types-changed-to-internal)
- [<span data-ttu-id="beb82-149">MVC. Удалена оболочка совместимости веб-интерфейса API</span><span class="sxs-lookup"><span data-stu-id="beb82-149">MVC: Web API compatibility shim removed</span></span>](#mvc-web-api-compatibility-shim-removed)
- [<span data-ttu-id="beb82-150">Razor. Компиляция среды выполнения перемещена в пакет</span><span class="sxs-lookup"><span data-stu-id="beb82-150">Razor: Runtime compilation moved to a package</span></span>](#razor-runtime-compilation-moved-to-a-package)
- [<span data-ttu-id="beb82-151">Состояние сеанса. Удалены устаревшие API</span><span class="sxs-lookup"><span data-stu-id="beb82-151">Session state: Obsolete APIs removed</span></span>](#session-state-obsolete-apis-removed)
- [<span data-ttu-id="beb82-152">Общая платформа. Из Microsoft.AspNetCore.App удалена сборка</span><span class="sxs-lookup"><span data-stu-id="beb82-152">Shared framework: Assembly removal from Microsoft.AspNetCore.App</span></span>](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [<span data-ttu-id="beb82-153">Общая платформа. Удален Microsoft.AspNetCore.All</span><span class="sxs-lookup"><span data-stu-id="beb82-153">Shared framework: Microsoft.AspNetCore.All removed</span></span>](#shared-framework-removed-microsoftaspnetcoreall)
- [<span data-ttu-id="beb82-154">SignalR. Заменен HandshakeProtocol.SuccessHandshakeData</span><span class="sxs-lookup"><span data-stu-id="beb82-154">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [<span data-ttu-id="beb82-155">SignalR. Удалены методы HubConnection</span><span class="sxs-lookup"><span data-stu-id="beb82-155">SignalR: HubConnection methods removed</span></span>](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [<span data-ttu-id="beb82-156">SignalR. Изменены конструкторы HubConnectionContext</span><span class="sxs-lookup"><span data-stu-id="beb82-156">SignalR: HubConnectionContext constructors changed</span></span>](#signalr-hubconnectioncontext-constructors-changed)
- [<span data-ttu-id="beb82-157">SignalR. Изменено имя пакета клиента JavaScript</span><span class="sxs-lookup"><span data-stu-id="beb82-157">SignalR: JavaScript client package name change</span></span>](#signalr-javascript-client-package-name-changed)
- [<span data-ttu-id="beb82-158">SignalR. Протокол MessagePack для концентратора перемещен в пакет MessagePack 2.x</span><span class="sxs-lookup"><span data-stu-id="beb82-158">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>](#signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package)
- [<span data-ttu-id="beb82-159">SignalR. Тип параметров протокола концентратора MessagePack изменился</span><span class="sxs-lookup"><span data-stu-id="beb82-159">SignalR: MessagePack Hub Protocol options type changed</span></span>](#signalr-messagepack-hub-protocol-options-type-changed)
- [<span data-ttu-id="beb82-160">SignalR. Устаревшие API</span><span class="sxs-lookup"><span data-stu-id="beb82-160">SignalR: Obsolete APIs</span></span>](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [<span data-ttu-id="beb82-161">SignalR. Методы UseSignalR и UseConnections удалены</span><span class="sxs-lookup"><span data-stu-id="beb82-161">SignalR: UseSignalR and UseConnections methods removed</span></span>](#signalr-usesignalr-and-useconnections-methods-removed)
- [<span data-ttu-id="beb82-162">Одностраничные приложения. Изменено поведение по умолчанию при переключении на средство ведения журнала консоли SpaServices и NodeServices</span><span class="sxs-lookup"><span data-stu-id="beb82-162">SPAs: SpaServices and NodeServices console logger fallback default change</span></span>](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [<span data-ttu-id="beb82-163">Одностраничные приложения. SpaServices и NodeServices отмечены как устаревшие</span><span class="sxs-lookup"><span data-stu-id="beb82-163">SPAs: SpaServices and NodeServices marked obsolete</span></span>](#spas-spaservices-and-nodeservices-marked-obsolete)
- [<span data-ttu-id="beb82-164">Статические файлы. Тип содержимого CSV изменен на соответствующий стандартам</span><span class="sxs-lookup"><span data-stu-id="beb82-164">Static files: CSV content type changed to standards-compliant</span></span>](#static-files-csv-content-type-changed-to-standards-compliant)
- [<span data-ttu-id="beb82-165">Целевая платформа: прекращена поддержка .NET Framework</span><span class="sxs-lookup"><span data-stu-id="beb82-165">Target framework: .NET Framework not supported</span></span>](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-50"></a><span data-ttu-id="beb82-166">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="beb82-166">ASP.NET Core 5.0</span></span>

[!INCLUDE[Azure: Microsoft-prefixed Azure integration packages removed](~/includes/core-changes/aspnetcore/5.0/azure-integration-packages-removed.md)]

***

[!INCLUDE[Extensions: Package reference changes](~/includes/core-changes/aspnetcore/5.0/extensions-package-reference-changes.md)]

***

[!INCLUDE[HTTP: HttpClient instances created by IHttpClientFactory log integer status codes](~/includes/core-changes/aspnetcore/5.0/http-httpclient-instances-log-integer-status-codes.md)]

***

[!INCLUDE[HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced](~/includes/core-changes/aspnetcore/5.0/http-badhttprequestexception-obsolete.md)]

***

[!INCLUDE[Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed](~/includes/core-changes/aspnetcore/5.0/localization-members-removed.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-package.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol options type changed](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-hub-protocol-options-changed.md)]

***

[!INCLUDE[SignalR: UseSignalR and UseConnections methods removed](~/includes/core-changes/aspnetcore/5.0/signalr-usesignalr-useconnections-removed.md)]

***

[!INCLUDE[Static files: CSV content type changed to standards-compliant](~/includes/core-changes/aspnetcore/5.0/static-files-csv-content-type-changed.md)]

***

## <a name="aspnet-core-31"></a><span data-ttu-id="beb82-167">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="beb82-167">ASP.NET Core 3.1</span></span>

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a><span data-ttu-id="beb82-168">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="beb82-168">ASP.NET Core 3.0</span></span>

[!INCLUDE[Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed](~/includes/core-changes/aspnetcore/3.0/obsolete-apis-removed.md)]

***

[!INCLUDE[Authentication: Google+ deprecation](~/includes/core-changes/aspnetcore/3.0/authn-google-plus-authn-changes.md)]

***

[!INCLUDE[Authentication: HttpContext.Authentication property removed](~/includes/core-changes/aspnetcore/3.0/authn-httpcontext-property-removed.md)]

***

[!INCLUDE[Authentication: Newtonsoft.Json types replaced](~/includes/core-changes/aspnetcore/3.0/authn-apis-json-types.md)]

***

[!INCLUDE[Authentication: OAuthHandler ExchangeCodeAsync signature changed](~/includes/core-changes/aspnetcore/3.0/authn-exchangecodeasync-signature-change.md)]

***

[!INCLUDE[Authorization: AddAuthorization overload assembly change](~/includes/core-changes/aspnetcore/3.0/authz-assembly-change.md)]

***

[!INCLUDE[Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters](~/includes/core-changes/aspnetcore/3.0/authz-iallowanonymous-removed-from-collection.md)]

***

[!INCLUDE[Authorization: IAuthorizationPolicyProvider implementations require new method](~/includes/core-changes/aspnetcore/3.0/authz-iauthzpolicyprovider-new-method.md)]

***

[!INCLUDE[Caching: CompactOnMemoryPressure property removed](~/includes/core-changes/aspnetcore/3.0/caching-memory-property-removed.md)]

***

[!INCLUDE[Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package](~/includes/core-changes/aspnetcore/3.0/caching-new-sqlclient-package.md)]

***

[!INCLUDE[Caching: ResponseCaching types changed to internal](~/includes/core-changes/aspnetcore/3.0/caching-response-pubternal-to-internal.md)]

***

[!INCLUDE[Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs](~/includes/core-changes/aspnetcore/3.0/dataprotection-azstorage-using-azstorage-apis.md)]

***

[!INCLUDE[Hosting: ANCM version 1 removed from hosting bundle](~/includes/core-changes/aspnetcore/3.0/hosting-ancmv1-hosting-bundle-removal.md)]

***

[!INCLUDE[Hosting: Generic host restriction on Startup constructor injection](~/includes/core-changes/aspnetcore/3.0/hosting-generic-host-startup-ctor-restriction.md)]

***

[!INCLUDE[Hosting: HTTPS redirection enabled for IIS OutOfProcess](~/includes/core-changes/aspnetcore/3.0/hosting-https-redirection-iis-outofprocess.md)]

***

[!INCLUDE[Hosting: IHostingEnvironment and IApplicationLifetime types replaced](~/includes/core-changes/aspnetcore/3.0/hosting-ihostingenv-iapplifetime-types-replaced.md)]

***

[!INCLUDE[Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies](~/includes/core-changes/aspnetcore/3.0/hosting-objectpoolprovider-webhostbuilder-dependencies.md)]

***

[!INCLUDE[HTTP: DefaultHttpContext extensibility removed](~/includes/core-changes/aspnetcore/3.0/http-defaulthttpcontext-extensibility-removed.md)]

***

[!INCLUDE[HTTP: HeaderNames fields changed to static readonly](~/includes/core-changes/aspnetcore/3.0/http-headernames-constants-staticreadonly.md)]

***

[!INCLUDE[HTTP: Response body infrastructure changes](~/includes/core-changes/aspnetcore/3.0/http-response-body-changes.md)]

***

[!INCLUDE[HTTP: Some cookie SameSite default values changed](~/includes/core-changes/aspnetcore/3.0/http-cookie-samesite-defaults-change.md)]

***

[!INCLUDE[HTTP: Synchronous IO disabled by default](~/includes/core-changes/aspnetcore/3.0/http-synchronous-io-disabled.md)]

***

[!INCLUDE[Identity: AddDefaultUI method overload removed](~/includes/core-changes/aspnetcore/3.0/identity-ui-adddefaultui-overload-removed.md)]

***

[!INCLUDE[Identity: UI Bootstrap version change](~/includes/core-changes/aspnetcore/3.0/identity-ui-bootstrap-version.md)]

***

[!INCLUDE[Identity: SignInAsync throws exception for unauthenticated identity](~/includes/core-changes/aspnetcore/3.0/identity-signinasync-throws-exception.md)]

***

[!INCLUDE[Identity: SignInManager constructor accepts new parameter](~/includes/core-changes/aspnetcore/3.0/identity-signinmanager-ctor-parameter.md)]

***

[!INCLUDE[Identity: UI uses static web assets feature](~/includes/core-changes/aspnetcore/3.0/identity-ui-static-web-assets.md)]

***

[!INCLUDE[Kestrel: Connection adapters removed](~/includes/core-changes/aspnetcore/3.0/kestrel-connection-adapters-removed.md)]

***

[!INCLUDE[Kestrel: Empty HTTPS assembly removed](~/includes/core-changes/aspnetcore/3.0/kestrel-empty-assembly-removed.md)]

***

[!INCLUDE[Kestrel: Request trailer headers moved to new collection](~/includes/core-changes/aspnetcore/3.0/kestrel-request-trailer-headers.md)]

***

[!INCLUDE[Kestrel: Transport abstraction layer changes](~/includes/core-changes/aspnetcore/3.0/kestrel-transport-abstractions.md)]

***

[!INCLUDE[Localization: APIs marked obsolete](~/includes/core-changes/aspnetcore/3.0/localization-apis-marked-obsolete.md)]

***

[!INCLUDE[Logging: DebugLogger class made internal](~/includes/core-changes/aspnetcore/3.0/logging-debuglogger-to-internal.md)]

***

[!INCLUDE[MVC: Controller action Async suffix removed](~/includes/core-changes/aspnetcore/3.0/mvc-action-async-suffix-trimmed.md)]

***

[!INCLUDE[MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core](~/includes/core-changes/aspnetcore/3.0/mvc-jsonresult-moved.md)]

***

[!INCLUDE[MVC: Precompilation tool deprecated](~/includes/core-changes/aspnetcore/3.0/mvc-precompilation-tool-deprecated.md)]

***

[!INCLUDE[MVC: Types changed to internal](~/includes/core-changes/aspnetcore/3.0/mvc-pubternal-to-internal.md)]

***

[!INCLUDE[MVC: Web API compatibility shim removed](~/includes/core-changes/aspnetcore/3.0/mvc-webapi-compat-shim-removed.md)]

***

[!INCLUDE[Razor: Runtime compilation moved to a package](~/includes/core-changes/aspnetcore/3.0/razor-runtime-compilation-package.md)]

***

[!INCLUDE[Session state: Obsolete APIs removed](~/includes/core-changes/aspnetcore/3.0/session-obsolete-apis-removed.md)]

***

[!INCLUDE[Shared framework: Assembly removal from Microsoft.AspNetCore.App](~/includes/core-changes/aspnetcore/3.0/sharedfx-app-shared-framework-assemblies.md)]

***

[!INCLUDE[Shared framework: Microsoft.AspNetCore.All removed](~/includes/core-changes/aspnetcore/3.0/sharedfx-all-framework-removed.md)]

***

[!INCLUDE[SignalR: HandshakeProtocol.SuccessHandshakeData replaced](~/includes/core-changes/aspnetcore/3.0/signalr-successhandshakedata-replaced.md)]

***

[!INCLUDE[SignalR: HubConnection methods removed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnection-methods-removed.md)]

***

[!INCLUDE[SignalR: HubConnectionContext constructors changed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnectioncontext-ctors.md)]

***

[!INCLUDE[SignalR: JavaScript client package name change](~/includes/core-changes/aspnetcore/3.0/signalr-js-client-package-name.md)]

***

[!INCLUDE[SignalR: Obsolete APIs](~/includes/core-changes/aspnetcore/3.0/signalr-obsolete-apis.md)]

***

[!INCLUDE[SPAs: SpaServices and NodeServices marked obsolete](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-obsolete.md)]

***

[!INCLUDE[SPAs: SpaServices and NodeServices console logger fallback default change](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-fallback.md)]

***

[!INCLUDE[Target framework: .NET Framework not supported](~/includes/core-changes/aspnetcore/3.0/targetfx-netfx-tfm-support.md)]

***
