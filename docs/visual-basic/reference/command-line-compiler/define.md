---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: cb56e727479fd249cb0d7e5e7c3c50d5b68b3a72
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072019"
---
# <a name="-define-visual-basic"></a>-define (Visual Basic)

Задает константы условной компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

or

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`symbol`|Обязательный. Определяемый символ.|  
|`value`|Необязательный элемент. Значение, которому назначается `symbol`. Если `value` является строкой, его необходимо заключить в последовательности из обратной косой черты и кавычки (\\"), а не просто в кавычки. Если значение не задано, считается, что используется значение True.|  
  
## <a name="remarks"></a>Примечания  

 Влияние параметра `-define` похоже на использование директивы препроцессора `#Const` в исходном файле, за исключением того, что определенные с помощью `-define` константы являются общими и применяются ко всем файлам в проекте.  
  
 Вы можете использовать символы, созданные этим параметром с помощью директивы `#If`...`Then`...`#Else`, для условной компиляции исходных файлов.  
  
 `-d` является краткой формой `-define`.  
  
 Вы можете определить несколько символов с помощью `-define`, разделяя их определения запятой.  
  
|Задание параметра -define в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно**.<br />4.  Измените значение в поле **Настраиваемые константы**.|  
  
## <a name="example"></a>Пример  

 В следующем примере кода определяются и используются две константы условной компиляции.  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Директивы #If...Then...#Else](../../language-reference/directives/if-then-else-directives.md)
- [Директива #Const](../../language-reference/directives/const-directive.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
