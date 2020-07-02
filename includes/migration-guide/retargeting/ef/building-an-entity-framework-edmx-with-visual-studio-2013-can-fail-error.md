---
ms.openlocfilehash: c5099f610569f7788bb829a2153006d20d8a4ea2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615760"
---
### <a name="building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>Построение EDMX Entity Framework с помощью Visual Studio 2013 может завершиться ошибкой MSB4062, если используются задачи EntityDeploySplit или EntityClean

#### <a name="details"></a>Подробнее

Инструменты MSBuild 12.0 (в составе Visual Studio 2013) изменили расположение файлов MSBuild, что привело к недействительности старых файлов целей построения Entity Framework. В результате задачи `EntityDeploySplit` и `EntityClean` завершаются ошибкой, так как они не могут найти `Microsoft.Data.Entity.Build.Tasks.dll`. Обратите внимание, что это нарушение возникает вследствие изменения набора инструментов (MSBuild и Visual Studio), а не из-за изменения платформы .NET Framework. Оно происходит только при обновлении средств разработчика, а не просто при обновлении .NET Framework.

#### <a name="suggestion"></a>Предложение

Начиная с .NET Framework 4.6 файлы целей построения Entity Framework предназначены для работы с новым макетом MSBuild. Проблема будет решена после обновления до этой версии. Кроме того, [это](https://stackoverflow.com/a/24249247/131944) решение можно использовать для исправления файлов целей построения напрямую.

| name    | Значение       |
|:--------|:------------|
| Область   | Значительно       |
| Version | 4.5.1       |
| Type    | Изменение целевой платформы |
