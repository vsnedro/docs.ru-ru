---
title: Критические изменения ASP.NET Core
titleSuffix: ''
description: В этой статье приведен список критических изменений в ASP.NET Core.
ms.date: 11/03/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: 6e8e35d01ea7ff91c45bf1febd822e8497b608f0
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440489"
---
# <a name="aspnet-core-breaking-changes"></a><span data-ttu-id="bf6a5-103">Критические изменения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bf6a5-103">ASP.NET Core breaking changes</span></span>

<span data-ttu-id="bf6a5-104">ASP.NET Core предоставляет функции разработки веб-приложений, используемые .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bf6a5-104">ASP.NET Core provides the web app development features used by .NET Core.</span></span>

<span data-ttu-id="bf6a5-105">Выберите одну из следующих ссылок для критических изменений в определенной версии.</span><span class="sxs-lookup"><span data-stu-id="bf6a5-105">Select one of the following links for breaking changes in a specific version:</span></span>

* [<span data-ttu-id="bf6a5-106">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="bf6a5-106">ASP.NET Core 5.0</span></span>](#aspnet-core-50)
* [<span data-ttu-id="bf6a5-107">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="bf6a5-107">ASP.NET Core 3.1</span></span>](#aspnet-core-31)
* [<span data-ttu-id="bf6a5-108">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bf6a5-108">ASP.NET Core 3.0</span></span>](#aspnet-core-30)

<span data-ttu-id="bf6a5-109">На этой странице описаны следующие критические изменения в ASP.NET Core версий 3.0, 3.1 и 5.0.</span><span class="sxs-lookup"><span data-stu-id="bf6a5-109">The following breaking changes in ASP.NET Core 3.0, 3.1, and 5.0 are documented on this page:</span></span>

- [<span data-ttu-id="bf6a5-110">Удалены устаревшие API в областях борьбы с фальсификацией, CORS, диагностики, MVC и маршрутизации</span><span class="sxs-lookup"><span data-stu-id="bf6a5-110">Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed</span></span>](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [<span data-ttu-id="bf6a5-111">Проверка подлинности. API-интерфейсы и пакеты AzureAD.UI и AzureADB2C.UI помечены как устаревшие</span><span class="sxs-lookup"><span data-stu-id="bf6a5-111">Authentication: AzureAD.UI and AzureADB2C.UI APIs and packages marked obsolete</span></span>](#authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete)
- [<span data-ttu-id="bf6a5-112">Проверка подлинности. Использование Google + прекращено</span><span class="sxs-lookup"><span data-stu-id="bf6a5-112">Authentication: Google+ deprecation</span></span>](#authentication-google-deprecated-and-replaced)
- [<span data-ttu-id="bf6a5-113">Проверка подлинности. Удалено свойство HttpContext.Authentication</span><span class="sxs-lookup"><span data-stu-id="bf6a5-113">Authentication: HttpContext.Authentication property removed</span></span>](#authentication-httpcontextauthentication-property-removed)
- [<span data-ttu-id="bf6a5-114">Проверка подлинности. Заменены типы Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="bf6a5-114">Authentication: Newtonsoft.Json types replaced</span></span>](#authentication-newtonsoftjson-types-replaced)
- [<span data-ttu-id="bf6a5-115">Проверка подлинности. Изменена подпись ExchangeCodeAsync OAuthHandler</span><span class="sxs-lookup"><span data-stu-id="bf6a5-115">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [<span data-ttu-id="bf6a5-116">Авторизация. Перегрузка AddAuthorization перемещена в другую сборку</span><span class="sxs-lookup"><span data-stu-id="bf6a5-116">Authorization: AddAuthorization overload moved to different assembly</span></span>](#authorization-addauthorization-overload-moved-to-different-assembly)
- [<span data-ttu-id="bf6a5-117">Авторизация. IAllowAnonymous удален из AuthorizationFilterContext.Filters</span><span class="sxs-lookup"><span data-stu-id="bf6a5-117">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [<span data-ttu-id="bf6a5-118">Авторизация. Для реализаций IAuthorizationPolicyProvider требуется новый метод</span><span class="sxs-lookup"><span data-stu-id="bf6a5-118">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [<span data-ttu-id="bf6a5-119">Авторизация. Для маршрутизации конечных точек используется ресурс HttpContext</span><span class="sxs-lookup"><span data-stu-id="bf6a5-119">Authorization: Resource in endpoint routing is HttpContext</span></span>](#authorization-resource-in-endpoint-routing-is-httpcontext)
- [<span data-ttu-id="bf6a5-120">Общие сведения Пакеты интеграции Azure с префиксом Майкрософт удалены</span><span class="sxs-lookup"><span data-stu-id="bf6a5-120">Azure: Microsoft-prefixed Azure integration packages removed</span></span>](#azure-microsoft-prefixed-azure-integration-packages-removed)
- [<span data-ttu-id="bf6a5-121">Методы сериализации BinaryFormatter устарели и запрещены в приложениях ASP.NET</span><span class="sxs-lookup"><span data-stu-id="bf6a5-121">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps)
- [<span data-ttu-id="bf6a5-122">Blazor. Незначащие пробелы удалены из компонентов во время компиляции</span><span class="sxs-lookup"><span data-stu-id="bf6a5-122">Blazor: Insignificant whitespace trimmed from components at compile time</span></span>](#blazor-insignificant-whitespace-trimmed-from-components-at-compile-time)
- [<span data-ttu-id="bf6a5-123">Blazor. Типы JSObjectReference и JSInProcessObjectReference изменены на internal</span><span class="sxs-lookup"><span data-stu-id="bf6a5-123">Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal</span></span>](#blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal)
- [<span data-ttu-id="bf6a5-124">Blazor. Функция ProtectedBrowserStorage перемещена на общую платформу</span><span class="sxs-lookup"><span data-stu-id="bf6a5-124">Blazor: ProtectedBrowserStorage feature moved to shared framework</span></span>](#blazor-protectedbrowserstorage-feature-moved-to-shared-framework)
- [<span data-ttu-id="bf6a5-125">Blazor. Открытые поля только для чтения RenderTreeFrame стали свойствами</span><span class="sxs-lookup"><span data-stu-id="bf6a5-125">Blazor: RenderTreeFrame readonly public fields have become properties</span></span>](#blazor-rendertreeframe-readonly-public-fields-have-become-properties)
- [<span data-ttu-id="bf6a5-126">Blazor. Изменена целевая платформа для пакетов NuGet</span><span class="sxs-lookup"><span data-stu-id="bf6a5-126">Blazor: Target framework of NuGet packages changed</span></span>](#blazor-target-framework-of-nuget-packages-changed)
- [<span data-ttu-id="bf6a5-127">Blazor. Обновлен список поддерживаемых веб-браузеров</span><span class="sxs-lookup"><span data-stu-id="bf6a5-127">Blazor: Updated browser support</span></span>](#blazor-updated-browser-support)
- [<span data-ttu-id="bf6a5-128">Blazor. Обновленная логика проверки для статических веб-ресурсов</span><span class="sxs-lookup"><span data-stu-id="bf6a5-128">Blazor: Updated validation logic for static web assets</span></span>](#blazor-updated-validation-logic-for-static-web-assets)
- [<span data-ttu-id="bf6a5-129">Кэширование. Удалено свойство CompactOnMemoryPressure</span><span class="sxs-lookup"><span data-stu-id="bf6a5-129">Caching: CompactOnMemoryPressure property removed</span></span>](#caching-compactonmemorypressure-property-removed)
- [<span data-ttu-id="bf6a5-130">Кэширование. Microsoft.Extensions.Caching.SqlServer использует новый пакет SqlClient</span><span class="sxs-lookup"><span data-stu-id="bf6a5-130">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [<span data-ttu-id="bf6a5-131">Кэширование. Типы ResponseCaching pubternal теперь стали внутренними</span><span class="sxs-lookup"><span data-stu-id="bf6a5-131">Caching: ResponseCaching "pubternal" types changed to internal</span></span>](#caching-responsecaching-pubternal-types-changed-to-internal)
- [<span data-ttu-id="bf6a5-132">Защита данных. DataProtection.Blobs использует новые API службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="bf6a5-132">Data Protection: DataProtection.Blobs uses new Azure Storage APIs</span></span>](#data-protection-dataprotectionblobs-uses-new-azure-storage-apis)
- [<span data-ttu-id="bf6a5-133">Расширения. Изменения ссылок на пакеты, затрагивающие некоторые пакеты NuGet</span><span class="sxs-lookup"><span data-stu-id="bf6a5-133">Extensions: Package reference changes affecting some NuGet packages</span></span>](#extensions-package-reference-changes-affecting-some-nuget-packages)
- [<span data-ttu-id="bf6a5-134">Размещение. Модуль AspNetCoreModule версии 1 удален из пакета размещения Windows</span><span class="sxs-lookup"><span data-stu-id="bf6a5-134">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [<span data-ttu-id="bf6a5-135">Размещение. Универсальный узел ограничивает внедрение через конструктор Startup</span><span class="sxs-lookup"><span data-stu-id="bf6a5-135">Hosting: Generic host restricts Startup constructor injection</span></span>](#hosting-generic-host-restricts-startup-constructor-injection)
- [<span data-ttu-id="bf6a5-136">Размещение. Для приложений IIS вне процесса включено перенаправление HTTPS</span><span class="sxs-lookup"><span data-stu-id="bf6a5-136">Hosting: HTTPS redirection enabled for IIS out-of-process apps</span></span>](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [<span data-ttu-id="bf6a5-137">Размещение. Удалены типы IHostingEnvironment и IApplicationLifetime</span><span class="sxs-lookup"><span data-stu-id="bf6a5-137">Hosting: IHostingEnvironment and IApplicationLifetime types replaced</span></span>](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="bf6a5-138">Размещение. ObjectPoolProvider удален из зависимостей WebHostBuilder</span><span class="sxs-lookup"><span data-stu-id="bf6a5-138">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [<span data-ttu-id="bf6a5-139">HTTP. Типы Kestrel и IIS BadHttpRequestException, помеченные как устаревшие и замененные</span><span class="sxs-lookup"><span data-stu-id="bf6a5-139">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>](#http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="bf6a5-140">HTTP. Изменения SameSite в браузере влияют на проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="bf6a5-140">HTTP: Browser SameSite changes impact authentication</span></span>](#http-browser-samesite-changes-impact-authentication)
- [<span data-ttu-id="bf6a5-141">HTTP. Удалена расширяемость DefaultHttpContext</span><span class="sxs-lookup"><span data-stu-id="bf6a5-141">HTTP: DefaultHttpContext extensibility removed</span></span>](#http-defaulthttpcontext-extensibility-removed)
- [<span data-ttu-id="bf6a5-142">HTTP. Поля HeaderNames изменены на статические только для чтения</span><span class="sxs-lookup"><span data-stu-id="bf6a5-142">HTTP: HeaderNames fields changed to static readonly</span></span>](#http-headernames-constants-changed-to-static-readonly)
- [<span data-ttu-id="bf6a5-143">HTTP. Экземпляры HttpClient, созданные с помощью целочисленных кодов состояния журнала IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="bf6a5-143">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>](#http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes)
- [<span data-ttu-id="bf6a5-144">HTTP. Изменения в инфраструктуре текста ответа</span><span class="sxs-lookup"><span data-stu-id="bf6a5-144">HTTP: Response body infrastructure changes</span></span>](#http-response-body-infrastructure-changes)
- [<span data-ttu-id="bf6a5-145">HTTP. Внесены изменения в некоторые значения по умолчанию для параметра SameSite для файлов cookie</span><span class="sxs-lookup"><span data-stu-id="bf6a5-145">HTTP: Some cookie SameSite default values changed</span></span>](#http-some-cookie-samesite-defaults-changed-to-none)
- [<span data-ttu-id="bf6a5-146">HTTP. Синхронный ввод-вывода отключен по умолчанию</span><span class="sxs-lookup"><span data-stu-id="bf6a5-146">HTTP: Synchronous IO disabled by default</span></span>](#http-synchronous-io-disabled-in-all-servers)
- [<span data-ttu-id="bf6a5-147">HttpSys: Повторное согласование сертификата клиента по умолчанию отключено</span><span class="sxs-lookup"><span data-stu-id="bf6a5-147">HttpSys: Client certificate renegotiation disabled by default</span></span>](#httpsys-client-certificate-renegotiation-disabled-by-default)
- [<span data-ttu-id="bf6a5-148">Удостоверение. Удалена перегрузка метода AddDefaultUI</span><span class="sxs-lookup"><span data-stu-id="bf6a5-148">Identity: AddDefaultUI method overload removed</span></span>](#identity-adddefaultui-method-overload-removed)
- [<span data-ttu-id="bf6a5-149">Удостоверение. Изменена версия начальной загрузки пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="bf6a5-149">Identity: UI Bootstrap version change</span></span>](#identity-default-bootstrap-version-of-ui-changed)
- [<span data-ttu-id="bf6a5-150">Удостоверение. SignInAsync создает исключение для удостоверения, не прошедшего проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="bf6a5-150">Identity: SignInAsync throws exception for unauthenticated identity</span></span>](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [<span data-ttu-id="bf6a5-151">Удостоверение. Конструктор SignInManager принимает новый параметр</span><span class="sxs-lookup"><span data-stu-id="bf6a5-151">Identity: SignInManager constructor accepts new parameter</span></span>](#identity-signinmanager-constructor-accepts-new-parameter)
- [<span data-ttu-id="bf6a5-152">Удостоверение. Пользовательский интерфейс использует функцию статических веб-ресурсов</span><span class="sxs-lookup"><span data-stu-id="bf6a5-152">Identity: UI uses static web assets feature</span></span>](#identity-ui-uses-static-web-assets-feature)
- [<span data-ttu-id="bf6a5-153">IIS: строки запросов ПО промежуточного слоя UrlRewrite сохраняются</span><span class="sxs-lookup"><span data-stu-id="bf6a5-153">IIS: UrlRewrite middleware query strings are preserved</span></span>](#iis-urlrewrite-middleware-query-strings-are-preserved)
- [<span data-ttu-id="bf6a5-154">Kestrel. Обнаружение изменений конфигурации во время выполнения включено по умолчанию</span><span class="sxs-lookup"><span data-stu-id="bf6a5-154">Kestrel: Configuration changes at run time detected by default</span></span>](#kestrel-configuration-changes-at-run-time-detected-by-default)
- [<span data-ttu-id="bf6a5-155">Kestrel. Удалены адаптеры подключений</span><span class="sxs-lookup"><span data-stu-id="bf6a5-155">Kestrel: Connection adapters removed</span></span>](#kestrel-connection-adapters-removed)
- [<span data-ttu-id="bf6a5-156">Kestrel. Изменены поддерживаемые версии протокола TLS по умолчанию</span><span class="sxs-lookup"><span data-stu-id="bf6a5-156">Kestrel: Default supported TLS protocol versions changed</span></span>](#kestrel-default-supported-tls-protocol-versions-changed)
- [<span data-ttu-id="bf6a5-157">Kestrel. Удалена пустая сборка HTTPS</span><span class="sxs-lookup"><span data-stu-id="bf6a5-157">Kestrel: Empty HTTPS assembly removed</span></span>](#kestrel-empty-https-assembly-removed)
- [<span data-ttu-id="bf6a5-158">Kestrel. HTTP/2 по TLS отключен в несовместимых версиях Windows</span><span class="sxs-lookup"><span data-stu-id="bf6a5-158">Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions</span></span>](#kestrel-http2-disabled-over-tls-on-incompatible-windows-versions)
- [<span data-ttu-id="bf6a5-159">Kestrel. Транспорт Libuv помечен как устаревший</span><span class="sxs-lookup"><span data-stu-id="bf6a5-159">Kestrel: Libuv transport marked as obsolete</span></span>](#kestrel-libuv-transport-marked-as-obsolete)
- [<span data-ttu-id="bf6a5-160">Kestrel. Заголовки трейлеров запросов перемещены в новую коллекцию</span><span class="sxs-lookup"><span data-stu-id="bf6a5-160">Kestrel: Request trailer headers moved to new collection</span></span>](#kestrel-request-trailer-headers-moved-to-new-collection)
- [<span data-ttu-id="bf6a5-161">Kestrel. Внесены изменения в слой абстракции транспорта</span><span class="sxs-lookup"><span data-stu-id="bf6a5-161">Kestrel: Transport abstraction layer changes</span></span>](#kestrel-transport-abstractions-removed-and-made-public)
- [<span data-ttu-id="bf6a5-162">Локализация. Интерфейсы API отмечены как устаревшие</span><span class="sxs-lookup"><span data-stu-id="bf6a5-162">Localization: APIs marked obsolete</span></span>](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [<span data-ttu-id="bf6a5-163">Локализация. Удалены API-интерфейсы Pubternal</span><span class="sxs-lookup"><span data-stu-id="bf6a5-163">Localization: "Pubternal" APIs removed</span></span>](#localization-pubternal-apis-removed)
- [<span data-ttu-id="bf6a5-164">Локализация. Из ПО промежуточного слоя локализации запроса удален устаревший конструктор</span><span class="sxs-lookup"><span data-stu-id="bf6a5-164">Localization: Obsolete constructor removed in request localization middleware</span></span>](#localization-obsolete-constructor-removed-in-request-localization-middleware)
- [<span data-ttu-id="bf6a5-165">Локализация. Удален класс ResourceManagerWithCultureStringLocalizer и элемент интерфейса WithCulture</span><span class="sxs-lookup"><span data-stu-id="bf6a5-165">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>](#localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed)
- [<span data-ttu-id="bf6a5-166">Ведение журнала. Класс DebugLogger стал внутренним</span><span class="sxs-lookup"><span data-stu-id="bf6a5-166">Logging: DebugLogger class made internal</span></span>](#logging-debuglogger-class-made-internal)
- [<span data-ttu-id="bf6a5-167">ПО промежуточного слоя. Страница ошибок базы данных помечена как устаревшая</span><span class="sxs-lookup"><span data-stu-id="bf6a5-167">Middleware: Database error page marked as obsolete</span></span>](#middleware-database-error-page-marked-as-obsolete)
- [<span data-ttu-id="bf6a5-168">ПО промежуточного слоя. ПО промежуточного слоя обработчика исключений создает исходное исключение, если обработчик не найден</span><span class="sxs-lookup"><span data-stu-id="bf6a5-168">Middleware: Exception Handler Middleware throws original exception if handler not found</span></span>](#middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found)
- [<span data-ttu-id="bf6a5-169">MVC. Удален асинхронный суффикс действия контроллера</span><span class="sxs-lookup"><span data-stu-id="bf6a5-169">MVC: Controller action Async suffix removed</span></span>](#mvc-async-suffix-trimmed-from-controller-action-names)
- [<span data-ttu-id="bf6a5-170">MVC. JsonResult перемещен в Microsoft.AspNetCore.Mvc.Core</span><span class="sxs-lookup"><span data-stu-id="bf6a5-170">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [<span data-ttu-id="bf6a5-171">MVC. ObjectModelValidator вызывает новую перегрузку ValidationVisitor.Validate</span><span class="sxs-lookup"><span data-stu-id="bf6a5-171">MVC: ObjectModelValidator calls a new overload of ValidationVisitor.Validate</span></span>](#mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate)
- [<span data-ttu-id="bf6a5-172">MVC. Использование средства предварительной компиляции прекращено</span><span class="sxs-lookup"><span data-stu-id="bf6a5-172">MVC: Precompilation tool deprecated</span></span>](#mvc-precompilation-tool-deprecated)
- [<span data-ttu-id="bf6a5-173">MVC. Типы теперь стали внутренними</span><span class="sxs-lookup"><span data-stu-id="bf6a5-173">MVC: Types changed to internal</span></span>](#mvc-pubternal-types-changed-to-internal)
- [<span data-ttu-id="bf6a5-174">MVC. Удалена оболочка совместимости веб-интерфейса API</span><span class="sxs-lookup"><span data-stu-id="bf6a5-174">MVC: Web API compatibility shim removed</span></span>](#mvc-web-api-compatibility-shim-removed)
- [<span data-ttu-id="bf6a5-175">Razor. Удален API RazorTemplateEngine</span><span class="sxs-lookup"><span data-stu-id="bf6a5-175">Razor: RazorTemplateEngine API removed</span></span>](#razor-razortemplateengine-api-removed)
- [<span data-ttu-id="bf6a5-176">Razor. Компиляция среды выполнения перемещена в пакет</span><span class="sxs-lookup"><span data-stu-id="bf6a5-176">Razor: Runtime compilation moved to a package</span></span>](#razor-runtime-compilation-moved-to-a-package)
- [<span data-ttu-id="bf6a5-177">Безопасность. Удалена кодировка имен файлов cookie</span><span class="sxs-lookup"><span data-stu-id="bf6a5-177">Security: Cookie name encoding removed</span></span>](#security-cookie-name-encoding-removed)
- [<span data-ttu-id="bf6a5-178">Безопасность. Обновлены версии пакета NuGet IdentityModel</span><span class="sxs-lookup"><span data-stu-id="bf6a5-178">Security: IdentityModel NuGet package versions updated</span></span>](#security-identitymodel-nuget-package-versions-updated)
- [<span data-ttu-id="bf6a5-179">Состояние сеанса. Удалены устаревшие API</span><span class="sxs-lookup"><span data-stu-id="bf6a5-179">Session state: Obsolete APIs removed</span></span>](#session-state-obsolete-apis-removed)
- [<span data-ttu-id="bf6a5-180">Общая платформа. Из Microsoft.AspNetCore.App удалена сборка</span><span class="sxs-lookup"><span data-stu-id="bf6a5-180">Shared framework: Assembly removal from Microsoft.AspNetCore.App</span></span>](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [<span data-ttu-id="bf6a5-181">Общая платформа. Удален Microsoft.AspNetCore.All</span><span class="sxs-lookup"><span data-stu-id="bf6a5-181">Shared framework: Microsoft.AspNetCore.All removed</span></span>](#shared-framework-removed-microsoftaspnetcoreall)
- [<span data-ttu-id="bf6a5-182">SignalR. Заменен HandshakeProtocol.SuccessHandshakeData</span><span class="sxs-lookup"><span data-stu-id="bf6a5-182">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [<span data-ttu-id="bf6a5-183">SignalR. Удалены методы HubConnection</span><span class="sxs-lookup"><span data-stu-id="bf6a5-183">SignalR: HubConnection methods removed</span></span>](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [<span data-ttu-id="bf6a5-184">SignalR. Изменены конструкторы HubConnectionContext</span><span class="sxs-lookup"><span data-stu-id="bf6a5-184">SignalR: HubConnectionContext constructors changed</span></span>](#signalr-hubconnectioncontext-constructors-changed)
- [<span data-ttu-id="bf6a5-185">SignalR. Изменено имя пакета клиента JavaScript</span><span class="sxs-lookup"><span data-stu-id="bf6a5-185">SignalR: JavaScript client package name change</span></span>](#signalr-javascript-client-package-name-changed)
- [<span data-ttu-id="bf6a5-186">SignalR. Протокол MessagePack для концентратора перемещен в пакет MessagePack 2.x</span><span class="sxs-lookup"><span data-stu-id="bf6a5-186">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>](#signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package)
- [<span data-ttu-id="bf6a5-187">SignalR. Тип параметров протокола концентратора MessagePack изменился</span><span class="sxs-lookup"><span data-stu-id="bf6a5-187">SignalR: MessagePack Hub Protocol options type changed</span></span>](#signalr-messagepack-hub-protocol-options-type-changed)
- [<span data-ttu-id="bf6a5-188">SignalR. Устаревшие API</span><span class="sxs-lookup"><span data-stu-id="bf6a5-188">SignalR: Obsolete APIs</span></span>](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [<span data-ttu-id="bf6a5-189">SignalR. Методы UseSignalR и UseConnections удалены</span><span class="sxs-lookup"><span data-stu-id="bf6a5-189">SignalR: UseSignalR and UseConnections methods removed</span></span>](#signalr-usesignalr-and-useconnections-methods-removed)
- [<span data-ttu-id="bf6a5-190">Одностраничные приложения. Изменено поведение по умолчанию при переключении на средство ведения журнала консоли SpaServices и NodeServices</span><span class="sxs-lookup"><span data-stu-id="bf6a5-190">SPAs: SpaServices and NodeServices console logger fallback default change</span></span>](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [<span data-ttu-id="bf6a5-191">Одностраничные приложения. SpaServices и NodeServices отмечены как устаревшие</span><span class="sxs-lookup"><span data-stu-id="bf6a5-191">SPAs: SpaServices and NodeServices marked obsolete</span></span>](#spas-spaservices-and-nodeservices-marked-obsolete)
- [<span data-ttu-id="bf6a5-192">Статические файлы. Тип содержимого CSV изменен на соответствующий стандартам</span><span class="sxs-lookup"><span data-stu-id="bf6a5-192">Static files: CSV content type changed to standards-compliant</span></span>](#static-files-csv-content-type-changed-to-standards-compliant)
- [<span data-ttu-id="bf6a5-193">Blazor WebAssembly не поддерживает интерфейсы API System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="bf6a5-193">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>](#systemsecuritycryptography-apis-not-supported-on-blazor-webassembly)
- [<span data-ttu-id="bf6a5-194">Целевая платформа: прекращена поддержка .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bf6a5-194">Target framework: .NET Framework not supported</span></span>](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-50"></a><span data-ttu-id="bf6a5-195">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="bf6a5-195">ASP.NET Core 5.0</span></span>

[!INCLUDE[Authentication: AzureAD.UI and AzureADB2C.UI APIs and packages marked obsolete](~/includes/core-changes/aspnetcore/5.0/authentication-aad-packages-obsolete.md)]

***

[!INCLUDE[Authorization: Resource in endpoint routing is HttpContext](~/includes/core-changes/aspnetcore/5.0/authorization-resource-in-endpoint-routing.md)]

<span data-ttu-id="bf6a5-196">\*\*_</span><span class="sxs-lookup"><span data-stu-id="bf6a5-196">\*\*_</span></span>

[!INCLUDE[Azure: Microsoft-prefixed Azure integration packages removed](~/includes/core-changes/aspnetcore/5.0/azure-integration-packages-removed.md)]

_*_

[!INCLUDE[Serialization: BinaryFormatter serialization obsolete](~/includes/core-changes/corefx/5.0/binaryformatter-serialization-obsolete.md)]

_*_

[!INCLUDE[Blazor: Insignificant whitespace trimmed from components at compile time](~/includes/core-changes/aspnetcore/5.0/blazor-components-trim-insignificant-whitespace.md)]

_*_

[!INCLUDE[Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal](~/includes/core-changes/aspnetcore/5.0/blazor-jsobjectreference-to-internal.md)]

_*_

[!INCLUDE[Blazor: ProtectedBrowserStorage feature moved to shared framework](~/includes/core-changes/aspnetcore/5.0/blazor-protectedbrowserstorage-moved.md)]

_*_

[!INCLUDE[Blazor: RenderTreeFrame readonly public fields have become properties](~/includes/core-changes/aspnetcore/5.0/blazor-rendertreeframe-fields-become-properties.md)]

_*_

[!INCLUDE[Blazor: Target framework of NuGet packages changed](~/includes/core-changes/aspnetcore/5.0/blazor-packages-target-framework-changed.md)]

_*_

[!INCLUDE[Blazor: Updated browser support](~/includes/core-changes/aspnetcore/5.0/blazor-browser-support-updated.md)]

_*_

[!INCLUDE[Blazor: Static web assets validation logic updated](~/includes/core-changes/aspnetcore/5.0/blazor-static-web-assets-validation-logic-updated.md)]

_*_

[!INCLUDE[Extensions: Package reference changes](~/includes/core-changes/aspnetcore/5.0/extensions-package-reference-changes.md)]

_*_

[!INCLUDE[HTTP: HttpClient instances created by IHttpClientFactory log integer status codes](~/includes/core-changes/aspnetcore/5.0/http-httpclient-instances-log-integer-status-codes.md)]

_*_

[!INCLUDE[HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced](~/includes/core-changes/aspnetcore/5.0/http-badhttprequestexception-obsolete.md)]

_*_

[!INCLUDE[HttpSys: Client certificate renegotiation disabled by default](~/includes/core-changes/aspnetcore/5.0/httpsys-client-certificate-renegotiation-disabled-by-default.md)]

_*_

[!INCLUDE[IIS: UrlRewrite middleware query strings are preserved](~/includes/core-changes/aspnetcore/5.0/iis-urlrewrite-middleware-query-strings-are-preserved.md)]

_*_

[!INCLUDE[Kestrel: Configuration changes at run time detected by default](~/includes/core-changes/aspnetcore/5.0/kestrel-configuration-changes-at-run-time-detected-by-default.md)]

_*_
[!INCLUDE[Kestrel: Default supported TLS protocol versions changed](~/includes/core-changes/aspnetcore/5.0/kestrel-default-supported-tls-protocol-versions-changed.md)]

_*_

[!INCLUDE[Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions](~/includes/core-changes/aspnetcore/5.0/kestrel-disables-http2-over-tls.md)]

_*_

[!INCLUDE[Kestrel: Libuv transport marked as obsolete](~/includes/core-changes/aspnetcore/5.0/kestrel-libuv-transport-obsolete.md)]

_*_

[!INCLUDE[Localization: "Pubternal" APIs removed](~/includes/core-changes/aspnetcore/5.0/localization-pubternal-apis-removed.md)]

_*_

[!INCLUDE[Localization: Obsolete constructor removed in request localization middleware](~/includes/core-changes/aspnetcore/5.0/localization-requestlocalizationmiddleware-constructor-removed.md)]

_*_

[!INCLUDE[Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed](~/includes/core-changes/aspnetcore/5.0/localization-members-removed.md)]

_*_

[!INCLUDE[Middleware: Database error page marked as obsolete](~/includes/core-changes/aspnetcore/5.0/middleware-database-error-page-obsolete.md)]

_*_

[!INCLUDE[Middleware: Exception Handler Middleware throws original exception if handler not found](~/includes/core-changes/aspnetcore/5.0/middleware-exception-handler-throws-original-exception.md)]

_*_

[!INCLUDE[MVC: ObjectModelValidator calls a new overload of ValidationVisitor.Validate](~/includes/core-changes/aspnetcore/5.0/mvc-objectmodelvalidator-calls-new-overload.md)]

_*_

[!INCLUDE[Security: Cookie name encoding removed](~/includes/core-changes/aspnetcore/5.0/security-cookie-name-encoding-removed.md)]

_*_

[!INCLUDE[Security: IdentityModel NuGet package versions updated](~/includes/core-changes/aspnetcore/5.0/security-identitymodel-nuget-package-versions-updated.md)]

_*_

[!INCLUDE[SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-package.md)]

_*_

[!INCLUDE[SignalR: MessagePack Hub Protocol options type changed](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-hub-protocol-options-changed.md)]

_*_

[!INCLUDE[SignalR: UseSignalR and UseConnections methods removed](~/includes/core-changes/aspnetcore/5.0/signalr-usesignalr-useconnections-removed.md)]

_*_

[!INCLUDE[Cryptography APIs not supported on Blazor WebAssembly](~/includes/core-changes/cryptography/5.0/cryptography-apis-not-supported-on-blazor-webassembly.md)]

_*_

[!INCLUDE[Static files: CSV content type changed to standards-compliant](~/includes/core-changes/aspnetcore/5.0/static-files-csv-content-type-changed.md)]

_*_

## <a name="aspnet-core-31"></a><span data-ttu-id="bf6a5-197">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="bf6a5-197">ASP.NET Core 3.1</span></span>

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

_*_

## <a name="aspnet-core-30"></a><span data-ttu-id="bf6a5-198">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bf6a5-198">ASP.NET Core 3.0</span></span>

[!INCLUDE[Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed](~/includes/core-changes/aspnetcore/3.0/obsolete-apis-removed.md)]

_*_

[!INCLUDE[Authentication: Google+ deprecation](~/includes/core-changes/aspnetcore/3.0/authn-google-plus-authn-changes.md)]

_*_

[!INCLUDE[Authentication: HttpContext.Authentication property removed](~/includes/core-changes/aspnetcore/3.0/authn-httpcontext-property-removed.md)]

_*_

[!INCLUDE[Authentication: Newtonsoft.Json types replaced](~/includes/core-changes/aspnetcore/3.0/authn-apis-json-types.md)]

_*_

[!INCLUDE[Authentication: OAuthHandler ExchangeCodeAsync signature changed](~/includes/core-changes/aspnetcore/3.0/authn-exchangecodeasync-signature-change.md)]

_*_

[!INCLUDE[Authorization: AddAuthorization overload assembly change](~/includes/core-changes/aspnetcore/3.0/authz-assembly-change.md)]

_*_

[!INCLUDE[Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters](~/includes/core-changes/aspnetcore/3.0/authz-iallowanonymous-removed-from-collection.md)]

_*_

[!INCLUDE[Authorization: IAuthorizationPolicyProvider implementations require new method](~/includes/core-changes/aspnetcore/3.0/authz-iauthzpolicyprovider-new-method.md)]

_*_

[!INCLUDE[Caching: CompactOnMemoryPressure property removed](~/includes/core-changes/aspnetcore/3.0/caching-memory-property-removed.md)]

_*_

[!INCLUDE[Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package](~/includes/core-changes/aspnetcore/3.0/caching-new-sqlclient-package.md)]

_*_

[!INCLUDE[Caching: ResponseCaching types changed to internal](~/includes/core-changes/aspnetcore/3.0/caching-response-pubternal-to-internal.md)]

_*_

[!INCLUDE[Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs](~/includes/core-changes/aspnetcore/3.0/dataprotection-azstorage-using-azstorage-apis.md)]

_*_

[!INCLUDE[Hosting: ANCM version 1 removed from hosting bundle](~/includes/core-changes/aspnetcore/3.0/hosting-ancmv1-hosting-bundle-removal.md)]

_*_

[!INCLUDE[Hosting: Generic host restriction on Startup constructor injection](~/includes/core-changes/aspnetcore/3.0/hosting-generic-host-startup-ctor-restriction.md)]

_*_

[!INCLUDE[Hosting: HTTPS redirection enabled for IIS OutOfProcess](~/includes/core-changes/aspnetcore/3.0/hosting-https-redirection-iis-outofprocess.md)]

_*_

[!INCLUDE[Hosting: IHostingEnvironment and IApplicationLifetime types replaced](~/includes/core-changes/aspnetcore/3.0/hosting-ihostingenv-iapplifetime-types-replaced.md)]

_*_

[!INCLUDE[Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies](~/includes/core-changes/aspnetcore/3.0/hosting-objectpoolprovider-webhostbuilder-dependencies.md)]

_*_

[!INCLUDE[HTTP: DefaultHttpContext extensibility removed](~/includes/core-changes/aspnetcore/3.0/http-defaulthttpcontext-extensibility-removed.md)]

_*_

[!INCLUDE[HTTP: HeaderNames fields changed to static readonly](~/includes/core-changes/aspnetcore/3.0/http-headernames-constants-staticreadonly.md)]

_*_

[!INCLUDE[HTTP: Response body infrastructure changes](~/includes/core-changes/aspnetcore/3.0/http-response-body-changes.md)]

_*_

[!INCLUDE[HTTP: Some cookie SameSite default values changed](~/includes/core-changes/aspnetcore/3.0/http-cookie-samesite-defaults-change.md)]

_*_

[!INCLUDE[HTTP: Synchronous IO disabled by default](~/includes/core-changes/aspnetcore/3.0/http-synchronous-io-disabled.md)]

_*_

[!INCLUDE[Identity: AddDefaultUI method overload removed](~/includes/core-changes/aspnetcore/3.0/identity-ui-adddefaultui-overload-removed.md)]

_*_

[!INCLUDE[Identity: UI Bootstrap version change](~/includes/core-changes/aspnetcore/3.0/identity-ui-bootstrap-version.md)]

_*_

[!INCLUDE[Identity: SignInAsync throws exception for unauthenticated identity](~/includes/core-changes/aspnetcore/3.0/identity-signinasync-throws-exception.md)]

_*_

[!INCLUDE[Identity: SignInManager constructor accepts new parameter](~/includes/core-changes/aspnetcore/3.0/identity-signinmanager-ctor-parameter.md)]

_*_

[!INCLUDE[Identity: UI uses static web assets feature](~/includes/core-changes/aspnetcore/3.0/identity-ui-static-web-assets.md)]

_*_

[!INCLUDE[Kestrel: Connection adapters removed](~/includes/core-changes/aspnetcore/3.0/kestrel-connection-adapters-removed.md)]

_*_

[!INCLUDE[Kestrel: Empty HTTPS assembly removed](~/includes/core-changes/aspnetcore/3.0/kestrel-empty-assembly-removed.md)]

_*_

[!INCLUDE[Kestrel: Request trailer headers moved to new collection](~/includes/core-changes/aspnetcore/3.0/kestrel-request-trailer-headers.md)]

_*_

[!INCLUDE[Kestrel: Transport abstraction layer changes](~/includes/core-changes/aspnetcore/3.0/kestrel-transport-abstractions.md)]

_*_

[!INCLUDE[Localization: APIs marked obsolete](~/includes/core-changes/aspnetcore/3.0/localization-apis-marked-obsolete.md)]

_*_

[!INCLUDE[Logging: DebugLogger class made internal](~/includes/core-changes/aspnetcore/3.0/logging-debuglogger-to-internal.md)]

_*_

[!INCLUDE[MVC: Controller action Async suffix removed](~/includes/core-changes/aspnetcore/3.0/mvc-action-async-suffix-trimmed.md)]

_*_

[!INCLUDE[MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core](~/includes/core-changes/aspnetcore/3.0/mvc-jsonresult-moved.md)]

_*_

[!INCLUDE[MVC: Precompilation tool deprecated](~/includes/core-changes/aspnetcore/3.0/mvc-precompilation-tool-deprecated.md)]

_*_

[!INCLUDE[MVC: Types changed to internal](~/includes/core-changes/aspnetcore/3.0/mvc-pubternal-to-internal.md)]

_*_

[!INCLUDE[MVC: Web API compatibility shim removed](~/includes/core-changes/aspnetcore/3.0/mvc-webapi-compat-shim-removed.md)]

_*_

[!INCLUDE[Razor: RazorTemplatEengine API removed](~/includes/core-changes/aspnetcore/3.0/razor-razortemplateengine-api-removed.md)]

_*_

[!INCLUDE[Razor: Runtime compilation moved to a package](~/includes/core-changes/aspnetcore/3.0/razor-runtime-compilation-package.md)]

_*_

[!INCLUDE[Session state: Obsolete APIs removed](~/includes/core-changes/aspnetcore/3.0/session-obsolete-apis-removed.md)]

_*_

[!INCLUDE[Shared framework: Assembly removal from Microsoft.AspNetCore.App](~/includes/core-changes/aspnetcore/3.0/sharedfx-app-shared-framework-assemblies.md)]

_*_

[!INCLUDE[Shared framework: Microsoft.AspNetCore.All removed](~/includes/core-changes/aspnetcore/3.0/sharedfx-all-framework-removed.md)]

_*_

[!INCLUDE[SignalR: HandshakeProtocol.SuccessHandshakeData replaced](~/includes/core-changes/aspnetcore/3.0/signalr-successhandshakedata-replaced.md)]

_*_

[!INCLUDE[SignalR: HubConnection methods removed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnection-methods-removed.md)]

_*_

[!INCLUDE[SignalR: HubConnectionContext constructors changed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnectioncontext-ctors.md)]

_*_

[!INCLUDE[SignalR: JavaScript client package name change](~/includes/core-changes/aspnetcore/3.0/signalr-js-client-package-name.md)]

_*_

[!INCLUDE[SignalR: Obsolete APIs](~/includes/core-changes/aspnetcore/3.0/signalr-obsolete-apis.md)]

_*_

[!INCLUDE[SPAs: SpaServices and NodeServices marked obsolete](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-obsolete.md)]

_*_

[!INCLUDE[SPAs: SpaServices and NodeServices console logger fallback default change](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-fallback.md)]

_*_

[!INCLUDE[Target framework: .NET Framework not supported](~/includes/core-changes/aspnetcore/3.0/targetfx-netfx-tfm-support.md)]

<span data-ttu-id="bf6a5-199">_\*\*</span><span class="sxs-lookup"><span data-stu-id="bf6a5-199">_\*\*</span></span>
