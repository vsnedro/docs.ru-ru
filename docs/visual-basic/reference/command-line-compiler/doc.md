---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
ms.openlocfilehash: 57a81983278c26090c62995f4da55c5cbfd66047
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408677"
---
# <a name="-doc"></a>-doc
Обрабатывает комментарии к документации в XML-файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-doc[+ | -]  
```

or  

```console
-doc:file  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательный элемент. Если задать + или `-doc`, компилятор создаст документацию и поместит ее в XML-файл. Если задать `-`, что эквивалентно отсутствию `-doc`, компилятор не будет создавать документацию.|  
|`file`|Является обязательным, если используется параметр `-doc:`. Определяет выходной XML-файл, который заполняется комментариями из файлов исходного кода, участвующих в компиляции. Если имя файла содержит пробел, заключите его в кавычки (" ").|  
  
## <a name="remarks"></a>Примечания  
 Параметр `-doc` определяет, будет ли компилятор создавать XML-файл, содержащий комментарии. Если вы используете синтаксис `-doc:file`, параметр `file` определяет имя XML-файла. Если вы используете `-doc` или `-doc+`, компилятор использует имя XML-файла из исполняемого файла или библиотеки, создаваемой компилятором. Если вы используете `-doc-` или не задаете параметр `-doc`, компилятор не создает XML-файл.  
  
 В файлах исходного кода комментарии к документации могут предшествовать таким определениям:  
  
- определяемые пользователем типы, такие как [class](../../language-reference/statements/class-statement.md) или [interface](../../language-reference/statements/interface-statement.md);  
  
- члены, такие как field, [event](../../language-reference/statements/event-statement.md), [property](../../language-reference/statements/property-statement.md), [function](../../language-reference/statements/function-statement.md) или [subroutine](../../language-reference/statements/sub-statement.md).  
  
 Чтобы использовать созданный XML-файл с помощью такой функции Visual Studio, как [IntelliSense](/visualstudio/ide/using-intellisense), имя XML-файла должно совпадать с именем сборки. Убедитесь, что XML-файл находится в том же каталоге, что и сборка, чтобы при обращении к сборке в проекте Visual Studio XML-файл мог бы также быть найден. XML-файлы документации не являются обязательными для работы IntelliSense с кодом в рамках одного или нескольких проектов, на которые ссылается проект.  
  
 XML-файл содержит теги `<assembly></assembly>`, если сборка не выполняется с помощью `-target:module`. Эти теги указывают имя файла, содержащего манифест сборки для выходного файла компиляции.  
  
 Способы создания документации из комментариев в коде описаны в разделе об [XML-тегах комментариев](../../language-reference/xmldoc/index.md).  
  
|Настройка параметра -doc в интегрированной среде разработки Visual Studio|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Задайте значение в поле **Создать XML-файл документации**.|  
  
## <a name="example"></a>Пример  
 Пример см. в статье [Документирование кода с помощью XML-комментариев](../../programming-guide/program-structure/documenting-your-code-with-xml.md).  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Документирование кода с помощью XML](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
