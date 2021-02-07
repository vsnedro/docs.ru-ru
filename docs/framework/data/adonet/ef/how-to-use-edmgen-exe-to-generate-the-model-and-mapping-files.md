---
description: Дополнительные сведения см. в статье как использовать EdmGen.exe для создания файлов модели и сопоставления.
title: Практическое руководство. Использование EdmGen.exe для создания файлов модели и сопоставления
ms.date: 03/30/2017
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
ms.openlocfilehash: b601e7dd3c108f4bf4966df2fabcf8324365fe3c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697417"
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>Практическое руководство. Использование EdmGen.exe для создания файлов модели и сопоставления

В этом разделе показано, как с помощью средства «Генератор модели EDM» (EdmGen.exe) на основе базы данных School формируются следующие файлы:  
  
- Концептуальная модель (CSDL-файл).  
  
- Модель хранения (SSDL-файл).  
  
- Сопоставление между концептуальной моделью и моделью хранения (MSL-файл).  
  
- Код уровня объекта в Visual Basic или C#.  
  
- Просмотр файлов.  
  
 Средство EdmGen.exe использует ключ /mode:FullGeneration для создания перечисленных выше файлов. Дополнительные сведения о EdmGen.exe командах см. в разделе [генератор EDM (EdmGen.exe)](edm-generator-edmgen-exe.md).  
  
 Если для создания файлов модели и сопоставления используется EdmGen.exe, по-прежнему необходимо настроить проект Visual Studio для использования Entity Framework. Дополнительные сведения см. [в разделе как вручную настроить проект Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).  
  
> [!NOTE]
> Концептуальная модель, созданная с помощью средства EdmGen.exe, включает все объекты базы данных. При необходимости создания концептуальной модели, включающей только определенные объекты, следует использовать мастер моделей EDM. Дополнительные сведения см. в разделе [инструкции. Использование мастера EDM](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Создание модели School для проекта Visual Basic с помощью программы EdmGen.exe  
  
1. Создайте базу данных School. Дополнительные сведения см. [в разделе Создание образца базы данных School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Выполните в командной строке следующую команду (введя ее без разрывов строк):  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>Создание модели School для проекта C# с помощью программы EdmGen.exe  
  
1. Создайте базу данных School. Дополнительные сведения см. [в разделе Создание образца базы данных School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Выполните в командной строке следующую команду (введя ее без разрывов строк):  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>См. также

- [Моделирование и сопоставление](modeling-and-mapping.md)
- [Практическое руководство. Настройка проекта Entity Framework вручную](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Практическое руководство. Предварительное создание представлений для повышения производительности запросов](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Средства EDM ADO.NET](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Практическое руководство. Использование EdmGen.exe для проверки файлов модели и сопоставления](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
