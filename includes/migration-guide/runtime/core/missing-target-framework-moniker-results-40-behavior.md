---
ms.openlocfilehash: 26a001ec2009a1a66dd9038b9bd3a42d7bcefb73
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620583"
---
### <a name="missing-target-framework-moniker-results-in-40-behavior"></a>Отсутствие моникера целевой платформы приводит к поведению версии 4.0

#### <a name="details"></a>Подробнее

Приложения без атрибута <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>, примененного на уровне сборки, будут автоматически запускаться с использованием семантики (особенностей) платформы .NET Framework 4.0. Для обеспечения высокого качества рекомендуется явным образом применить ко всем двоичным файлам атрибут <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>, указывающий версию платформы .NET Framework, в которой они были созданы. Обратите внимание, что при использовании моникера целевой платформы в файле проекта MSBuild будет автоматически применять <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>.

#### <a name="suggestion"></a>Предложение

Атрибут <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> должен быть предоставлен либо путем его добавления непосредственно в сборку, либо путем указания целевой платформы в [файле проекта или с помощью графического интерфейса свойств проекта Visual Studio](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).

| name    | Значение       |
|:--------|:------------|
| Область   |Значительно|
|Version|4.5|
|Type|Среда выполнения|
