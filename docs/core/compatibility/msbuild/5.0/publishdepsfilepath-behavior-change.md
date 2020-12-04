---
title: Критическое изменение. Изменение поведения PublishDepsFilePath
description: Сведения о критическом изменении в .NET 5.0, где свойство MSBuild PublishDepsFilePath пусто для однофайловых приложений.
ms.date: 09/17/2020
ms.openlocfilehash: 70631beff31aa3388e59f3b79875ef437351451a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760295"
---
# <a name="publishdepsfilepath-behavior-change"></a>Изменение поведения PublishDepsFilePath

Свойство MSBuild `PublishDepsFilePath` пусто для однофайловых приложений. Кроме того, для приложений с несколькими файлами файл *deps.json* может быть скопирован в выходной каталог только на более поздних этапах сборки.

## <a name="version-introduced"></a>Представленная версия

5.0

## <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET свойство MSBuild `PublishDepsFilePath` является путем к файлу *deps.json* приложения в выходном каталоге для приложений с несколькими файлами и путем в промежуточном каталоге для однофайловых приложений.

Начиная с .NET 5.0 свойство `PublishDepsFilePath` пусто для однофайловых приложений, а новое свойство `IntermediateDepsFilePath` указывает расположение файла *deps.json* в промежуточном каталоге. Кроме того, для приложений с несколькими файлами файл *deps.json* может быть скопирован в выходной каталог (т. е. по пути, указанному в `PublishDepsFilePath`) только на более поздних этапах сборки.

## <a name="reason-for-change"></a>Причина изменения

Это изменение было внесено по нескольким причинам.

- Из-за рефакторинга логики публикации для поддержки [улучшенных однофайловых приложений](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) в .NET 5.

- Для защиты однофайловых приложений от целевых объектов, которые пытаются перезаписать файл *deps.json* уже после его объединения в пакет, без влияния на приложение. Поэтому свойство MSBuild `PublishDepsFilePath` пусто для однофайловых приложений.

## <a name="recommended-action"></a>Рекомендованное действие

Целевые объекты, которые перезаписывают файл *deps.json*, обычно используют для этого свойство `IntermediateDepsFilePath`.

## <a name="affected-apis"></a>Затронутые API

Н/Д

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
