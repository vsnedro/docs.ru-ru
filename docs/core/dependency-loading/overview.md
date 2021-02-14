---
title: Загрузка зависимостей (.NET Core)
description: Общие сведения об управляемой и неуправляемой загрузке зависимостей в .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.topic: overview
ms.openlocfilehash: 2eaa01fad3913272dc90891592d0e35cd89ad2ab
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506322"
---
# <a name="dependency-loading-in-net-core"></a>Загрузка зависимостей в .NET Core

Каждое приложение .NET Core имеет некоторые зависимости. Даже самое простое приложение `hello world` зависит от нескольких разделов в библиотеках классов .NET Core.

Понимание стандартной логики загрузки сборок .NET Core поможет разобраться в типичных проблемах с развертыванием и отлаживать их.

В некоторых приложениях зависимости определяются динамически во время выполнения. В таких ситуациях важно понимать, как загружаются управляемые и неуправляемые сборки.

## <a name="understanding-assemblyloadcontext"></a>Основные сведения об AssemblyLoadContext

API <xref:System.Runtime.Loader.AssemblyLoadContext> является важнейшей частью системы загрузки в .NET Core. Статья [Основные сведения об AssemblyLoadContext](understanding-assemblyloadcontext.md) содержит высокоуровневое описание этой системы.

## <a name="loading-details"></a>Загрузка сведений

Сведения об алгоритме загрузки кратко упоминаются в нескольких статьях:

- [Алгоритм загрузки управляемых сборок](loading-managed.md)
- [Алгоритм загрузки вспомогательных сборок](loading-resources.md)
- [Алгоритм загрузки неуправляемых (собственных) библиотек](loading-unmanaged.md)
- [Стандартное зондирование](default-probing.md)

## <a name="create-a-net-core-application-with-plugins"></a>Создание приложения .NET Core с подключаемыми модулями

В руководстве [Создание приложения .NET Core с подключаемыми модулями](../tutorials/creating-app-with-plugin-support.md) описывается создание настраиваемого AssemblyLoadContext. Он использует <xref:System.Runtime.Loader.AssemblyDependencyResolver> для разрешения зависимостей подключаемого модуля. Этот учебник правильно изолирует зависимости подключаемого модуля от ведущего приложения.

## <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a>Использование и отладка сборок с возможностью выгрузки в .NET Core

Пошаговые инструкции см. в статье [Использование и отладка сборок с возможностью выгрузки в .NET Core](../../standard/assembly/unloadability.md). В ней показано, как загрузить приложение .NET Core, выполнить и выгрузить его. Также в этой статье есть рекомендации по отладке.

## <a name="collect-detailed-assembly-loading-information"></a>Сбор подробных сведений о загрузке сборок

В статье [Сбор подробных сведений о загрузке сборок](collect-details.md) объясняется, как получить подробные сведения о загрузке управляемой сборки в среде выполнения. В рамках той же статьи используется средство [dotnet-trace](../diagnostics/dotnet-trace.md) для записи событий загрузчика сборки в трассировку выполняемого процесса.
