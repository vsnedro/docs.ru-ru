---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 9e8146497d63d949f138d6cd08c9ea8c7b03c651
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414315"
---
# <a name="-addmodule"></a>-addmodule
Дает компилятору указание сделать всю информацию о типах из указанных файлов доступной компилируемому проекту.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>Аргументы  
 `fileList`  
 Обязательный. Разделенный запятыми список файлов, содержащих метаданные, но не содержащих манифесты сборки. Имена файлов, содержащие пробелы, должны быть заключены в кавычки (" ").  
  
## <a name="remarks"></a>Примечания  
 Файлы, перечисленные в параметре `fileList`, должны быть созданы с использованием параметра `-target:module` или параметра, эквивалентного `-target:module`, в другом компиляторе.  
  
 Все модули, добавленные с помощью `-addmodule`, во время выполнения должны находиться в том же каталоге, что и выходной файл. То есть во время компиляции можно указать модуль в любом каталоге, но во время выполнения он должен находиться в каталоге приложения. В противном случае возникает ошибка <xref:System.TypeLoadException>.  
  
 При указании (неявно или явно) любого параметра [-target (Visual Basic)](target.md), кроме `-target:module` с `-addmodule`, файлы, передаваемые в `-addmodule`, становятся частью сборки проекта. Сборка необходима для запуска выходного файла, который содержит один или несколько файлов, добавленных с помощью `-addmodule`.  
  
 Используйте параметр [-reference (Visual Basic)](reference.md) для импорта метаданных из файла, содержащего сборку.  
  
> [!NOTE]
> Параметр `-addmodule` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код создает модуль.  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 Следующий код импортирует типы модуля.  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 При запуске `t1` он выводит `802`.  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [-target (Visual Basic)](target.md)
- [-reference (Visual Basic)](reference.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
