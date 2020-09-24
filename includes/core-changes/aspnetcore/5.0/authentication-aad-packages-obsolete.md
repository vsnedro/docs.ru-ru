---
ms.openlocfilehash: 8bcd9987cb061233c8476b9c083a224fc0e25440
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539510"
---
### <a name="authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete"></a>Аутентификация. API-интерфейсы и пакеты AzureAD.UI и AzureADB2C.UI помечены как устаревшие

В ASP.NET Core 2.1 интеграцию с проверкой подлинности Azure Active Directory (Azure AD) и Azure Active Directory B2C (Azure AD B2C) обеспечивают пакеты [Microsoft.AspNetCore.Authentication.AzureAD.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureAD.UI) и [Microsoft.AspNetCore.Authentication.AzureADB2C.UI](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.AzureADB2C.UI). Функциональные возможности, предоставляемые этими пакетами, основаны на конечной точке Azure AD версии 1.0.

В ASP.NET Core 5.0 и более поздних версиях интеграцию с проверкой подлинности Azure AD и Azure AD B2C обеспечивает пакет [Microsoft.Identity.Web](https://www.nuget.org/packages/Microsoft.Identity.Web). Этот пакет основан на платформе Microsoft Identity, которая ранее называлась конечной точкой Azure AD версии 2.0. Следовательно, использовать старые API-интерфейсы в пакетах `Microsoft.AspNetCore.Authentication.AzureAD.UI` и `Microsoft.AspNetCore.Authentication.AzureADB2C.UI` не рекомендуется.

Обсуждение этого вопроса см. на странице GitHub [dotnet/aspnetcore#25807](https://github.com/dotnet/aspnetcore/issues/25807).

#### <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 8

#### <a name="old-behavior"></a>Старое поведение

API-интерфейсы не помечены как устаревшие.

#### <a name="new-behavior"></a>Новое поведение

API-интерфейсы помечены как устаревшие.

#### <a name="reason-for-change"></a>Причина изменения

Возможности проверки подлинности Azure AD и Azure AD B2C были перенесены в API-интерфейсы Библиотеки проверки подлинности Майкрософт (MSAL), предоставляемые `Microsoft.Identity.Web`.

#### <a name="recommended-action"></a>Рекомендованное действие

Следуйте указаниям по API `Microsoft.Identity.Web` для [веб-приложений](https://github.com/azuread/microsoft-identity-web/wiki/web-apps) и [веб-API](https://github.com/azuread/microsoft-identity-web/wiki/web-apis).

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

* [Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions](/dotnet/api/microsoft.aspnetcore.authentication.azureadauthenticationbuilderextensions?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureaddefaults?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions](/dotnet/api/microsoft.aspnetcore.authentication.azuread.ui.azureadoptions?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2cauthenticationbuilderextensions?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2cdefaults?view=aspnetcore-3.0)
* [Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions](/dotnet/api/microsoft.aspnetcore.authentication.azureadb2c.ui.azureadb2coptions?view=aspnetcore-3.0)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Authentication.AzureADAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureAD.UI.AzureADOptions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2CAuthenticationBuilderExtensions`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2CDefaults`
- `T:Microsoft.AspNetCore.Authentication.AzureADB2C.UI.AzureADB2COptions`

-->
