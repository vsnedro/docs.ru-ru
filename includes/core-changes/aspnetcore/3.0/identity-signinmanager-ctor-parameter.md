---
ms.openlocfilehash: ed5a90063b8963d79f412ec1c5c0b9030f980f83
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032790"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a>Удостоверение. конструктор SignInManager принимает новый параметр

Начиная с ASP.NET Core 3.0 в конструктор `SignInManager` был добавлен новый параметр `IUserConfirmation<TUser>`. Подробную информацию см. на странице [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="reason-for-change"></a>Причина изменения

Изменение позволит добавить поддержку новых потоков сообщений электронной почты и подтверждений в удостоверении.

#### <a name="recommended-action"></a>Рекомендованное действие

При создании `SignInManager` вручную предоставьте реализацию `IUserConfirmation` или воспользуйтесь реализацией из внедрения зависимостей.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
