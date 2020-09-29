---
description: -win32icon (параметры компилятора C#)
title: -win32icon (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
ms.openlocfilehash: 5b62bbfe28bb5aa82605a88a83cf82eff9278807
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168872"
---
# <a name="-win32icon-c-compiler-options"></a>-win32icon (параметры компилятора C#)

Параметр **-win32icon** вставляет в выходной файл ICO-файл, который придает выходному файлу необходимый вид в проводнике.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a>Аргументы  

 `filename`  
 ICO-файл, который требуется добавить в выходной файл.  
  
## <a name="remarks"></a>Remarks  

 ICO-файл можно создать с помощью [компилятора ресурсов](/windows/desktop/menurc/resource-compiler). Компилятор ресурсов вызывается при компиляции программы Visual C++; ICO-файл создается из RC-файла.  
  
 Дополнительные сведения о ссылках на файлы ресурсов .NET Framework и их присоединении см. в разделах [-linkresource](./linkresource-compiler-option.md) и [-resource](./resource-compiler-option.md) соответственно. Дополнительные сведения об импорте RES-файла см. в разделе [-win32res](./win32res-compiler-option.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1. Откройте страницу **Свойства** проекта.  
  
2. Перейдите на страницу свойств **Приложение**.  
  
3. Измените свойство **Значок приложения**.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в статье <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.  
  
## <a name="example"></a>Пример  

 Скомпилируйте `in.cs` и присоедините ICO-файл `rf.ico`, чтобы получить файл `in.exe`:  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a>См. также раздел

- [Параметры компилятора C# ](./index.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
