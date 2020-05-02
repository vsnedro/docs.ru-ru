---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: dd98b45d75ff421dc81666ed47695132a49bfa3a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524476"
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
  
 При указании (неявно или явно) любого параметра [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md), кроме `-target:module` с `-addmodule`, файлы, передаваемые в `-addmodule`, становятся частью сборки проекта. Сборка необходима для запуска выходного файла, который содержит один или несколько файлов, добавленных с помощью `-addmodule`.  
  
 Используйте параметр [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) для импорта метаданных из файла, содержащего сборку.  
  
> [!NOTE]
> Параметр `-addmodule` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код создает модуль.  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 Следующий код импортирует типы модуля.  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 При запуске `t1` он выводит `802`.  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
