---
title: 'NETSDK1071: PackageReference для "{0}" указывает версию `{1}`.'
description: Как устранить проблему с PackageReference для метапакета, включенного в состав платформы с версией.
author: Forgind
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1071
ms.openlocfilehash: 852232cba04bb93a17872280e10848c2896991ae
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445709"
---
# <a name="netsdk1071-explicitly-versioned-packagereference-to-a-metapackage-that-would-be-included-with-the-framework"></a>NETSDK1071: Явное управление версиями PackageReference для метапакета, который будет включаться в состав платформы.

**Эта статья относится к:** ✔️ пакету SDK для .NET 5.0.100 и более поздних версий

Когда пакет SDK для .NET выдает предупреждение NETSDK1071, это означает, что в будущем может возникнуть конфликт версий между версией метапакета, указанной в PackageReference, и версией того же метапакета, неявно заданной в свойстве TargetFramework:

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

Так как TargetFramework автоматически переносит версию метапакета, эти версии, если они различны, будут конфликтовать.

Чтобы устранить эту проблему:

1. При использовании .NET Core или .NET Standard следует избегать явных ссылок на `Microsoft.NETCore.App` или `NETStandard.Library` в файле проекта.
2. Если при ориентации на .NET Core нужна определенная версия среды выполнения, вместо прямой ссылки на метапакет используйте свойство `<RuntimeFrameworkVersion>`. Это может произойти, например, когда вы используете [автономные развертывания](../../deploying/index.md#publish-self-contained) и нуждаетесь в определенной версии исправления 1.0.0 LTS для среды выполнения.
3. Если при ориентации на .NET Standard вам нужна конкретная версия `NetStandard.Library`, можно использовать свойство `<NetStandardImplicitPackageVersion>` и установить требуемую версию.
4. Не добавляйте и не обновляйте ссылки на `Microsoft.NETCore.App` или `NETSTandard.Library` явным образом в проектах .NET Framework. Если при использовании пакета NuGet на основе .NET Standard требуется любая версия `NETStandard.Library`, NuGet автоматически устанавливает ее.
5. Не указывайте версию для `Microsoft.AspNetCore.App` или `Microsoft.AspNetCore.All` при использовании .NET Core 2.1+, так как пакет SDK для .NET Core автоматически выбирает соответствующую версию. (Примечание: Это работает только при нацеливании на .NET Core 2.1, если проект также использует `Microsoft.NET.Sdk.Web`. Эта проблема устранена в пакете SDK для .NET Core 2.2.)
6. Если вы не хотите получать это предупреждение, вы можете отключить его:

   ```xml
   <PackageReference Include="Microsoft.NetCore.App" Version="2.2.8" >
     <AllowExplicitVersion>true</AllowExplicitVersion>
   </PackageReference>
   ```
