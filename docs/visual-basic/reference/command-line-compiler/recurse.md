---
description: 'Дополнительные сведения: -recurse'
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 2c0f1788c3811e24e2d51ff30e4cb2842aa0bd7a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475881"
---
# <a name="-recurse"></a>-recurse

Компилирует файлы исходного кода во всех дочерних каталогах указанного каталога или каталога проекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Аргументы  

 `dir`  
 Необязательный элемент. Каталог, с которого будет начинаться поиск. Если не указать, поиск начинается в каталоге проекта.  
  
 `file`  
 Обязательный. Файлы для поиска. Поддерживаются подстановочные знаки.  
  
## <a name="remarks"></a>Примечания  

 Чтобы скомпилировать все соответствующие файлы в каталоге проекта, не задавая `-recurse`, можно использовать подстановочные знаки в именах файлов. Если имя выходного файла не указано, компилятор выводит имя выходного файла для первого обработанного входного файла. Обычно это первый файл в списке файлов, скомпилированных при просмотре в алфавитном порядке. По этой причине лучше определять выходной файл с помощью параметра `-out`.  
  
> [!NOTE]
> Параметр `-recurse` недоступен в среде разработки Visual Studio. Он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  

 Следующая команда компилирует все файлы Visual Basic в текущем каталоге.  
  
```console
vbc *.vb  
```  
  
 Следующая команда компилирует все файлы Visual Basic в каталоге `Test\ABC` и всех вложенных каталогах, а затем создает `Test.ABC.dll`.  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [-out (Visual Basic)](out.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
