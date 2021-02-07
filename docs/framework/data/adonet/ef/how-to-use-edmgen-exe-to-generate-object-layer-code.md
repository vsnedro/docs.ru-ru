---
description: Дополнительные сведения см. в статье как использовать EdmGen.exe для создания кода Object-Layer
title: Практическое руководство. Использование EdmGen.exe для создания кода объектного уровня
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 1c1f614247f10c8819709b9494fb1ec04271b634
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697469"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a>Практическое руководство. Использование EdmGen.exe для создания кода объектного уровня

В этом разделе показано, как использовать средство [генератора EDM (EdmGen.exe)](edm-generator-edmgen-exe.md) для создания кода уровня объекта на основе CSDL-файла.  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Создание кода уровня объекта для модели School в проекте Visual Basic с помощью EdmGen.exe  
  
1. Создайте базу данных School. Дополнительные сведения см. [в разделе Создание образца базы данных School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Создайте модель School или получите файл School.csdl. Дополнительные сведения см. в разделе [инструкции. использование EdmGen.exe для создания файлов модели и сопоставления](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3. Выполните в командной строке следующую команду (введя ее без разрывов строк):  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a>Создание кода уровня объектов для модели School в проекте С# с помощью программы EdmGen.exe  
  
1. Создайте базу данных School. Дополнительные сведения см. [в разделе Создание образца базы данных School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Создайте модель School или получите файл School.csdl. Дополнительные сведения см. в разделе [инструкции. использование EdmGen.exe для создания файлов модели и сопоставления](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3. Выполните в командной строке следующую команду (введя ее без разрывов строк):  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a>См. также

- [Моделирование и сопоставление](modeling-and-mapping.md)
- [Практическое руководство. Настройка проекта Entity Framework вручную](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Средства работы с моделью EDM ADO.NET](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Практическое руководство. Предварительное создание представлений для повышения производительности запросов](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Практическое руководство. Использование EdmGen.exe для создания файлов модели и сопоставления](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
