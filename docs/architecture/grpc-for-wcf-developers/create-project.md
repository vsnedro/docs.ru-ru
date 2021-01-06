---
title: Создание нового ASP.NET Core проекта gRPC — gRPC для разработчиков WCF
description: Узнайте, как создать проект gRPC с помощью Visual Studio или командной строки.
ms.date: 12/15/2020
ms.openlocfilehash: 960725a9507797f43b2c15283e384b0ad827c2b1
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938664"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a>Создание проекта ASP.NET Core gRPC

Пакет SDK для .NET поставляется с мощным средством CLI, `dotnet` которое позволяет создавать проекты и решения из командной строки и управлять ими. Пакет SDK тесно интегрирован с Visual Studio, поэтому все доступно также через знакомый графический пользовательский интерфейс. В этой главе показаны оба способа создания нового проекта ASP.NET Core gRPC.

## <a name="create-the-project-by-using-visual-studio"></a>Создание проекта с помощью Visual Studio

> [!IMPORTANT]
> Для разработки любого приложения ASP.NET Core 5,0 требуется Visual Studio 2019 версии 16,3 или более поздней, с установленной рабочей нагрузкой **ASP.NET и Web Development** .

Создайте пустое решение с именем **традерсис** из шаблона *пустого решения* . Добавьте папку решения с именем `src` . Затем щелкните правой кнопкой мыши папку и выберите команду **Добавить**  >  **Новый проект**. Введите `grpc` в поле поиска шаблона, и вы увидите шаблон проекта с именем `gRPC Service` .

![Снимок экрана: диалоговое окно "Добавление нового проекта"](media/create-project/new-grpc-project.png)

Нажмите кнопку **Далее** , чтобы перейти в диалоговое окно **Настройка нового проекта** . Присвойте проекту имя `TraderSys.Portfolios` и добавьте `src` подкаталог в **Расположение**.

![Снимок экрана: диалоговое окно "Настройка нового проекта"](media/create-project/configure-project.png)

Нажмите кнопку **Далее** , чтобы перейти к диалоговому окну **Создание новой службы gRPC** .

![Снимок экрана: диалоговое окно "Создание службы gRPC"](media/create-project/create-new-grpc-service-v2.png)

В настоящее время у вас есть ограниченные параметры для создания службы. DOCKER будет добавлен позднее, поэтому пока оставьте этот параметр невыбранным. Просто выберите **создать**. Будет создан первый проект ASP.NET Core 5,0 gRPC и добавлен в решение. Если вы не хотите больше узнать о работе с `dotnet CLI` , перейдите к разделу [Очистка кода примера](#clean-up-the-example-code) .

## <a name="create-the-project-by-using-the-net-cli"></a>Создание проекта с помощью интерфейса командной строки .NET

В этом разделе рассматривается создание решений и проектов из командной строки.

Создайте решение, как показано в следующей команде. `-o`Флаг (или `--output` ) указывает выходной каталог, который создается в текущем каталоге, если он еще не существует. Имя решения совпадает с именем каталога: `TraderSys.sln` . Можно указать другое имя с помощью `-n` `--name` флага (или).

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

ASP.NET Core 5,0 поставляется с шаблоном CLI для gRPC Services. Создайте новый проект с помощью этого шаблона, поместив его в `src` подкаталог, как обычный для проектов ASP.NET Core. Проект именуется после каталога ( `TraderSys.Portfolios.csproj` ), если не указано другое имя с `-n` флагом.

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

Наконец, добавьте проект в решение с помощью `dotnet sln` команды:

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> Поскольку конкретный каталог содержит только один `.csproj` файл, можно указать только каталог, чтобы сохранить ввод.

Теперь это решение можно открыть в Visual Studio 2019, Visual Studio Code или любом другом редакторе.

## <a name="clean-up-the-example-code"></a>Очистка кода примера

Теперь вы создали пример службы с помощью шаблона gRPC, который был рассмотрен ранее в книге. Этот код не полезен в нашем контексте торговли по акции, поэтому мы будем изменять вещи для нашего первого проекта.

### <a name="rename-and-edit-the-proto-file"></a>Переименование и изменение файла имени

Переименуйте файл в и `Protos/greet.proto` `Protos/portfolios.proto` откройте его в редакторе. Удалите все после `package` строки. Затем измените `option csharp_namespace` имена, `package` и `service` и удалите службу по умолчанию `SayHello` . Теперь код выглядит следующим образом:

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> Шаблон не добавляет `Protos` часть пространства имен по умолчанию, но его добавление упрощает создание gRPC классов и собственных классов, четко разделенных в коде.

Если переименовать `greet.proto` файл в интегрированной среде разработки (IDE), например в Visual Studio, ссылка на этот файл будет автоматически обновлена в `.csproj` файле. Но в другом редакторе, например Visual Studio Code, эта ссылка не обновляется автоматически, поэтому необходимо изменить файл проекта вручную.

В целевом gRPC сборках существует `Protobuf` элемент Item, позволяющий указать, какие `.proto` файлы следует компилировать, и какая из форм требуется для создания кода (то есть "сервер" или "клиент").

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a>Переименуйте `GreeterService` класс

`GreeterService`Класс находится в `Services` папке и наследует от `Greeter.GreeterBase` . Переименуйте его в `PortfolioService` и измените базовый класс на `Portfolios.PortfoliosBase` . Удалите `override` методы.

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

В методе класса существует ссылка на `GreeterService` класс `Configure` `Startup` . Если вы использовали рефакторинг для переименования класса, эта ссылка должна быть обновлена автоматически. Однако, если это не так, необходимо изменить его вручную.

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

В следующем разделе мы добавим функции к этой новой службе.

>[!div class="step-by-step"]
>[Назад](migrate-wcf-to-grpc.md)
>[Вперед](migrate-request-reply.md)
