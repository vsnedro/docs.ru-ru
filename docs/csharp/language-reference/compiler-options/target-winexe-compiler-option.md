---
description: -target:winexe (параметры компилятора C#)
title: -target:winexe (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 6e14a2aac427c7adfd69f66eaf624816b75f6ea2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168937"
---
# <a name="-targetwinexe-c-compiler-options"></a>-target:winexe (параметры компилятора C#)

Параметр **-target:winexe** предписывает компилятору создать исполняемый файл (EXE), программу Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a>Remarks  

 Исполняемый файл создается с расширением ЕХЕ. Программа Windows предоставляет пользовательский интерфейс либо из библиотеки .NET, либо с помощью API-интерфейсов Windows.  
  
 Воспользуйтесь параметром [-target:exe](./target-exe-compiler-option.md), чтобы создать консольное приложение.  
  
 Если не указано иное с помощью параметра [-out](./out-compiler-option.md), имя выходного файла совпадает с именем входного файла, который содержит метод [Main](../../programming-guide/main-and-command-args/index.md).  
  
 Для создания DLL-файла используются все файлы, указанные в командной строке вплоть до следующего параметра **-out** или [-target](./target-compiler-option.md).  
  
 В файлах исходного кода, который компилируется в EXE-файл, должен содержаться один и только один метод **Main**. Параметр [-main](./main-compiler-option.md) позволяет указывать класс, содержащий метод **Main**, в случаях, когда код содержит несколько классов с методом **Main**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1. Откройте страницу **Свойства** проекта.  
  
2. Перейдите на страницу свойств **Приложение**.  
  
3. Измените значение свойства **Тип выходных данных**.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в статье <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Пример  

 Компиляция `in.cs` в программу Windows:  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a>См. также раздел

- [-target (параметры компилятора C#)](./target-compiler-option.md)
- [Параметры компилятора C# ](./index.md)
