---
description: 'Дополнительные сведения: -out (Visual Basic)'
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 82fb43ecf2239c38245f3afe7cacef8bad573175
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475894"
---
# <a name="-out-visual-basic"></a>-out (Visual Basic)

Задает имя выходного файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`filename`|Обязательный. Имя выходного файла, создаваемого компилятором. Если имя файла содержит пробел, заключите его в кавычки (" ").|  
  
## <a name="remarks"></a>Примечания  

 Укажите полное имя и расширение создаваемого файла. В противном случае этот EXE-файл именуется по файлу исходного кода, содержащему процедуру `Sub Main`, а DLL-файл именуется по первому файлу исходного кода.  
  
 Если указать имя файла без расширения EXE или DLL, компилятор автоматически добавляет расширение в зависимости от значения, указанного для параметра компилятора `-target`.  
  
|Настройка параметра -out в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Перейдите на вкладку **Приложение** .<br />3.  Измените значение в поле **Имя сборки**.|  
  
## <a name="example"></a>Пример  

 Следующий код компилирует `T2.vb` и создает выходной файл `T2.exe`.  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [-target (Visual Basic)](target.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
