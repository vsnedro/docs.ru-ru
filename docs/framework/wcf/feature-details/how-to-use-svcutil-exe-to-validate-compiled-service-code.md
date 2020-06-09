---
title: Практическое руководство. Использование программы Svcutil.exe для проверки скомпилированного кода службы
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: 6f2064c696e3186c3208a7e57dc51655056d23ea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595353"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a>Практическое руководство. Использование программы Svcutil.exe для проверки скомпилированного кода службы
Для обнаружения ошибок в реализациях и конфигурациях служб без размещения службы можно использовать [средство служебной программы для метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) .  
  
### <a name="to-validate-a-service"></a>Проверка службы  
  
1. Скомпилируйте службу в исполняемый файл и одну или более зависимых сборок.  
  
2. Откройте окно командной строки SDK.  
  
3. Из командной строки запустите средство Svcutil.exe, используя следующий формат. Дополнительные сведения о различных параметрах см. в разделе Service Валидатионсектион of [ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) .  
  
    ```console
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     Чтобы указать имя конфигурации службы для проверки, необходимо использовать параметр `/serviceName`.  
  
     Аргумент `assemblyPath` задает путь к исполняемому файлу для службы и одной или более сборок, которые содержат типы службы для проверки. Исполняемая сборка должна содержать связанный файл конфигурации для предоставления конфигурации службы. Для предоставления нескольких сборок можно использовать стандартные подстановочные знаки командной строки.  
  
## <a name="example"></a>Пример  
 Следующая команда проверяет службу myServiceName, реализованную в исполняемом файле myServiceHost.exe.  Автоматически загружается файл конфигурации для этой службы (myServiceHost.exe.config).  
  
```console  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a>Дополнительно

- [Служебное средство ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
