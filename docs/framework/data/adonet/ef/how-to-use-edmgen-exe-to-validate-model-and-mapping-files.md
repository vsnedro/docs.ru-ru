---
description: Дополнительные сведения см. в статье как использовать EdmGen.exe для проверки файлов модели и сопоставления.
title: Практическое руководство. Использование EdmGen.exe для проверки файлов модели и сопоставления
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: e729ea36b7ff17dc318f4488a669b968161aea8b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697352"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>Практическое руководство. Использование EdmGen.exe для проверки файлов модели и сопоставления

В этом разделе показано, как использовать средство [генератора EDM (EdmGen.exe)](edm-generator-edmgen-exe.md) для проверки файлов модели и сопоставления. Дополнительные сведения см. в разделе [EDM](../entity-data-model.md).  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>Проверка модели School при помощи программы EdmGen.exe  
  
1. Создайте базу данных School. Дополнительные сведения см. [в разделе Создание образца базы данных School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Сформируйте модель School. Дополнительные сведения см. в разделе [инструкции. использование EdmGen.exe для создания файлов модели и сопоставления](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3. Выполните в командной строке следующую команду (введя ее без разрывов строк):  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Настройка проекта Entity Framework вручную](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Средства EDM ADO.NET](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Практическое руководство. Предварительное создание представлений для повышения производительности запросов](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Практическое руководство. Использование EdmGen.exe для создания кода объектного уровня](how-to-use-edmgen-exe-to-generate-object-layer-code.md)
