---
ms.openlocfilehash: 53840ddd59ae3463bae2930fd0151ab2cd2d65cb
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593333"
---
### <a name="design-time-builds-only-return-top-level-package-references"></a>Сборки времени разработки возвращают только ссылки на пакеты верхнего уровня

Начиная с пакета SDK для .NET Core 3.1.400 целевой `RunResolvePackageDependencies` возвращает только ссылки на пакеты верхнего уровня.

#### <a name="version-introduced"></a>Представленная версия

Пакет SDK для .NET Core 3.1.400

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях пакета SDK для .NET Core целевой объект `RunResolvePackageDependencies` создавал следующие элементы MSBuild, которые содержали информацию из файла ресурсов NuGet:

- `PackageDefinitions`
- `PackageDependencies`
- `TargetDefinitions`
- `FileDefinitions`
- `FileDependencies`

Эти данные используются в Visual Studio для заполнения узла зависимостей в обозревателе решений. Однако объем данных может быть большим, и эти данные не нужны, если узел зависимости не развернут.

Начиная с пакета SDK для .NET Core версии 3.1.400 большинство этих элементов не создается по умолчанию. Возвращаются только элементы типа `Package`. Если Visual Studio требуются элементы для заполнения узла зависимостей, он считывает информацию непосредственно из файла ресурсов.

#### <a name="reason-for-change"></a>Причина изменения

Это было введено для улучшения производительности при загрузке решения в Visual Studio. Ранее загружались все ссылки на пакеты, что приводило к загрузке множества ссылок, которые большинство пользователей никогда не увидят.

#### <a name="recommended-action"></a>Рекомендованное действие

Если логика MSBuild зависит от создаваемых элементов, задайте для свойства `EmitLegacyAssetsFileItems` в файле проекта значение `true`. Этот параметр включает предыдущее поведение, при котором создаются все элементы.

#### <a name="category"></a>Категория

MSBuild

#### <a name="affected-apis"></a>Затронутые API

Н/Д
