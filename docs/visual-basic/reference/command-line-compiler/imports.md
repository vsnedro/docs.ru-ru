---
description: 'Дополнительные сведения: -imports (Visual Basic)'
title: -imports
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 8c6744ff857a15da9362b724a62fcf053e9fd8f0
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100470204"
---
# <a name="-imports-visual-basic"></a>-imports (Visual Basic)

Импортирует пространства имен из указанной сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`namespaceList`|Обязательный. Разделенный запятыми список пространств имен для импорта.|  
  
## <a name="remarks"></a>Примечания  

 Параметр `-imports` импортирует любое пространство имен, определенное в текущем наборе исходных файлов или любой связанной сборке.  
  
 Элементы в пространстве имен, заданном с помощью `-imports`, доступны для всех файлов исходного кода в компиляции. Используйте [оператор Imports (пространство имен и тип .NET)](../../language-reference/statements/imports-statement-net-namespace-and-type.md), чтобы использовать пространство имен в одном файле исходного кода.  
  
|Настройка параметра -imports в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Перейдите на вкладку **Ссылки**.<br />3.  Введите имя пространства имен в поле рядом с кнопкой **Добавить пользовательский импорт**.<br />4.  Нажмите кнопку **Добавить пользовательский импорт**.|  
  
## <a name="example"></a>Пример  

 Следующий код компилируется, когда указан параметр `-imports:system.globalization`. В противном случае для успешной компиляции требуется, чтобы инструкция `Imports System.Globalization` была включена в начало файла исходного кода или чтобы свойство было полностью определено как `System.Globalization.CultureInfo.CurrentCulture.Name`.

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Ссылки и оператор Imports](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
