---
title: Для какой ОС использовать контейнеры .NET
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Для какой ОС использовать контейнеры .NET
ms.date: 01/13/2021
ms.openlocfilehash: 1b914d9afca9ade37f13e639f73001b91f338d26
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "98187991"
---
# <a name="what-os-to-target-with-net-containers"></a>Для какой ОС использовать контейнеры .NET

Учитывая разнообразие операционных систем, поддерживаемых Docker, и различия между .NET Framework и .NET 5, следует выбирать определенные ОС и определенные версии в зависимости от платформы, которую вы используете.

Для Windows можно использовать Windows Server Core или Windows Nano Server. Эти версии Windows предоставляют разные особенности (IIS в Windows Server Core или резидентный веб-сервер, такой как Kestrel, в Nano Server), которые могут быть необходимы в .NET Framework или .NET 5 соответственно.

Для Linux доступно и поддерживается множество дистрибутивов в официальных образах Docker .NET (например, Debian).

На рисунке 3-1 представлены возможные версии операционной системы в зависимости от используемой платформы .NET.

![Схема, на которой показано, какую ОС с какими контейнерами .NET следует использовать.](./media/net-container-os-targets/targeting-operating-systems.png)

**Рис. 3-1**. Выбираемые операционные системы в зависимости от версии платформы .NET

При развертывании устаревших приложений .NET Framework выберите в качестве целевой ОС Windows Server Core, которая совместима с устаревшими приложениями и службами IIS, но образ которой имеет больший размер. При развертывании приложений .NET 5 в качестве целевой ОС можно выбрать Windows Nano Server, которая оптимизирована для облака, использует Kestrel, имеет образ меньшого размера и запускается быстрее. В качестве целевой среды можно выбрать ОС Linux, которая поддерживает Debian, Alpine и другие дистрибутивы. Можете также использовать образ Kestrel, который имеет меньший размер и запускается быстрее.

В том случае, если требуется использовать другой дистрибутив Linux или если нужен образ с версиями, не предоставляемыми Майкрософт, можно также создать собственный образ Docker. Например, можно создать образ с ASP.NET Core для работы на классической платформе .NET Framework и в Windows Server Core, что для Docker является довольно редко используемым сценарием.

> [!IMPORTANT]
> При использовании образов Windows Server Core может оказаться, что отсутствуют некоторые библиотеки DLL по сравнению с полными образами Windows. Возможно, вы можете решить эту проблему, создав пользовательский образ Server Core и добавив отсутствующие файлы во время сборки, как описано в этом [комментарии на сайте GitHub](https://github.com/microsoft/dotnet-framework-docker/issues/299#issuecomment-511537448).

При добавлении имени образа в файл Dockerfile можно выбрать операционную систему и версию в зависимости от используемого тега, как показано в следующих примерах:

| Изображение | Комментарии |
|-------|----------|
| mcr.microsoft.com/dotnet/runtime:5.0 | .NET 5 (несколько архитектур): поддерживает Linux и Windows Nano Server в зависимости от узла Docker. |
| mcr.microsoft.com/dotnet/aspnet:5.0 | ASP.NET Core 5.0 (несколько архитектур): поддерживает Linux и Windows Nano Server в зависимости от узла Docker. <br/> Образ aspnetcore имеет несколько оптимизаций для ASP.NET Core. |
| mcr.microsoft.com/dotnet/aspnet:5.0-buster-slim | .NET 5(только для среды выполнения) на основе дистрибутива Linux Debian |
| mcr.microsoft.com/dotnet/aspnet:5.0-nanoserver-1809 | .NET 5 (только для среды выполнения) на основе Windows Nano Server (Windows Server версии 1809) |

## <a name="additional-resources"></a>Дополнительные ресурсы

- **BitmapDecoder завершается со сбоем из-за отсутствующей библиотеки WindowsCodecsExt.dll (проблема GitHub)**  
  <https://github.com/microsoft/dotnet-framework-docker/issues/299>

> [!div class="step-by-step"]
> [Назад](container-framework-choice-factors.md)
> [Вперед](official-net-docker-images.md)
