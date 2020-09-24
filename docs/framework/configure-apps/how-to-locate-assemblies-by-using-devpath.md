---
title: Практическое руководство. Поиск сборок с помощью DEVPATH
description: Проверьте, правильно ли работает общая сборка с множеством приложений в .NET, используя файл конфигурации компьютера XML и переменную среды DEVPATH.
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 8ae807e46b11d2adb06d6af0c86e1c7297caa0c0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161988"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>Практическое руководство. Поиск сборок с помощью DEVPATH

Разработчикам может потребоваться убедиться, что создаваемая ими общая сборка работает правильно с несколькими приложениями. Вместо постоянного размещения сборки в глобальном кэше сборок во время цикла разработки разработчик может создать переменную среды DEVPATH, которая указывает на выходной каталог сборки для сборки.  
  
 Например, предположим, что создается общая сборка с именем Мишаредассембли, а выходной каталог — К:\мишаредассембли\дебуг. К:\мишаредассембли\дебуг можно разместить в переменной DEVPATH. Затем необходимо указать [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) элемент в файле конфигурации компьютера. Этот элемент указывает среде CLR использовать DEVPATH для нахождение сборок.  
  
 Общая сборка должна быть обнаружена средой выполнения.  Чтобы указать частный каталог для разрешения ссылок на сборки, используйте [ \<codeBase> элемент](./file-schema/runtime/codebase-element.md) или [ \<probing> элемент](./file-schema/runtime/probing-element.md) в файле конфигурации, как описано в разделе [Указание расположения сборки](specify-assembly-location.md).  Также можно разместить сборку в подкаталоге каталога приложения. Дополнительные сведения см. [в разделе Обнаружение сборок в среде выполнения](../deployment/how-the-runtime-locates-assemblies.md).  
  
> [!NOTE]
> Это дополнительная функция, предназначенная только для разработки.  
  
 В следующем примере показано, как заставить среду выполнения искать сборки в каталогах, заданных переменной среды DEVPATH.  
  
## <a name="example"></a>Пример  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 По умолчанию этот параметр имеет значение false.  
  
> [!NOTE]
> Используйте этот параметр только во время разработки. Среда выполнения не проверяет версии сборок со строгими именами, найденных в DEVPATH. Он просто использует первую найденную сборку.  
  
## <a name="see-also"></a>См. также раздел

- [Настройка приложений с использованием файлов конфигурации](index.md)
