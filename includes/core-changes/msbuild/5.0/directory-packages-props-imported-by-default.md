---
ms.openlocfilehash: 4a916a4178535763712ebd58fde1a81e456da0d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538827"
---
### <a name="directorypackagesprops-files-is-imported-by-default"></a>Файлы Directory.Packages.props импортируются по умолчанию

Файлы *.props* NuGet автоматически импортируют файл с именем *Directory.Packages.props*, если он находится в папке проекта или любом из ее предков.

#### <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 8

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET в файле проекта у вас мог быть файл с именем *Directory.Packages.props*, который автоматически не импортировался файлом *.props* NuGet во время сборки.

Начиная с .NET 5.0 такой файл автоматически *импортируется*, если он существует в папке проекта или любом из ее предков. Если в папке проекта есть файл с таким именем, эта операция автоматического импорта может изменить поведение сборки. Например, файл будет импортирован, но не импортировался ранее, или порядок, в котором он импортируется, может измениться в случае его намеренного импорта.

#### <a name="reason-for-change"></a>Причина изменения

Это изменение было внесено для поддержки [централизованного управления версиями пакетов](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) для NuGet.

#### <a name="recommended-action"></a>Рекомендованное действие

Переименуйте существующий файл *Directory.Packages.props*, если он не должен импортироваться автоматически.

#### <a name="category"></a>Категория

MSBuild

#### <a name="affected-apis"></a>Затронутые API

Н/Д

<!--

#### Affected APIs

Not detectable via API analysis.

-->
