---
description: -target:library (параметры компилятора C#)
title: -target:library (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: 0f5b1e1bec8fd601bf111e1c2c64adf22d0a064e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193729"
---
# <a name="-targetlibrary-c-compiler-options"></a>-target:library (параметры компилятора C#)

Параметр **-target:library** заставляет компилятор создавать библиотеку динамической компоновки (DLL), а не исполняемый файл (EXE).  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a>Remarks  

 Библиотека DLL создается с расширением DLL.  
  
 Выходной файл получает имя первого входного файла, если только с помощью параметра [-out](./out-compiler-option.md) не указано иное.  
  
 Для создания DLL-файла используются все файлы, указанные в командной строке до следующего параметра **-out** или **-target: module**.  
  
 При построении библиотеки DLL метод [Main](../../programming-guide/main-and-command-args/index.md) не требуется.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1. Откройте страницу **Свойства** проекта.  
  
2. Перейдите на страницу свойств **Приложение**.  
  
3. Измените значение свойства **Тип выходных данных**.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в статье <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Пример  

 Компиляция файла`in.cs`, создание модуля `in.dll`:  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a>См. также раздел

- [-target (параметры компилятора C#)](./target-compiler-option.md)
- [Параметры компилятора C# ](./index.md)
