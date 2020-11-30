---
description: -recurse (параметры компилятора C#)
title: -recurse (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
ms.openlocfilehash: 9e84ff95f7f0addac1c2c2d79af0ab53572da27f
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193807"
---
# <a name="-recurse-c-compiler-options"></a>-recurse (параметры компилятора C#)

Параметр -recurse позволяет компилировать файлы исходного кода во всех вложенных каталогах заданного каталога (dir) или каталога проекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Аргументы  

 Среда `dir` (необязательно)  
 Каталог, с которого будет начинаться поиск. Если этот параметр не задан, поиск начинается с каталога проекта.  
  
 `file`  
 Файлы для поиска. Поддерживаются подстановочные знаки.  
  
## <a name="remarks"></a>Примечания  

 Параметр **-recurse** позволяет компилировать файлы исходного кода во всех вложенных каталогах заданного каталога (`dir`) или каталога проекта.  
  
 Чтобы скомпилировать все соответствующие файлы в каталоге проекта, не задавая параметр **-recurse**, можно использовать подстановочные знаки в именах файлов.  
  
 Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.  
  
## <a name="example"></a>Пример  

 Компиляция всех файлов C# в текущем каталоге:  
  
```console  
csc *.cs  
```  
  
 Компиляция всех файлов C# в каталоге dir1\dir2 и всех вложенных в него каталогах, а также создание файла dir2.dll:  
  
```console  
csc -target:library -out:dir2.dll -recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a>См. также раздел

- [Параметры компилятора C# ](./index.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
