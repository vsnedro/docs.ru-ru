---
title: Критические изменения MSBuild
description: В этой статье приведен список критических изменений в MSBuild для .NET Core 3.0–3.1.
ms.date: 12/14/2020
ms.openlocfilehash: 1ed5878845406fa7727c644f1e196d63a860646a
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593452"
---
# <a name="msbuild-breaking-changes-in-net-core-30---31"></a>Критические изменения MSBuild в .NET Core 3.0–3.1

На этой странице описаны следующие критические изменения:

| Критическое изменение | Представленная версия |
| - | - |
| [Сборки времени разработки возвращают только ссылки на пакеты верхнего уровня](#design-time-builds-only-return-top-level-package-references) | 3.1 |
| [Изменение имен файлов манифеста ресурса](#resource-manifest-file-name-change) | 3.0 |

## <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE [design-time-builds-return-top-level-package-refs](../../../includes/core-changes/msbuild/3.1/design-time-builds-return-top-level-package-refs.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***
