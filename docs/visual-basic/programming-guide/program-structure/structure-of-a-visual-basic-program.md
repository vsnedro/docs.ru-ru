---
title: Структура программы Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
ms.openlocfilehash: dc6b38d78f02a42c8e7cc2aa964e9f3f74996f44
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408768"
---
# <a name="structure-of-a-visual-basic-program"></a>Структура программы Visual Basic
Visual Basicная программа строится на основе стандартных блоков. *Решение* состоит из одного или нескольких проектов. *Проект* , в свою очередь, может содержать одну или несколько сборок. Каждая *Сборка* компилируется из одного или нескольких исходных файлов. *Исходный файл* предоставляет определение и реализацию классов, структур, модулей и интерфейсов, которые в конечном итоге содержат весь код.  
  
 Дополнительные сведения об этих стандартных блоках Visual Basic программы см. в разделе [решения и проекты](/visualstudio/ide/solutions-and-projects-in-visual-studio) и [сборки в .NET](../../../standard/assembly/index.md).  
  
## <a name="file-level-programming-elements"></a>Элементы программирования на уровне файлов  
 При запуске проекта или файла и открытии редактора кода вы увидите, что какой-то код уже существует и в правильном порядке. Любой код, который вы пишете, должен соответствовать следующей последовательности:  
  
1. `Option`инструкции  
  
2. `Imports`инструкции  
  
3. `Namespace`операторы и элементы уровня пространства имен  
  
 При вводе инструкций в другом порядке могут возникнуть ошибки компиляции.  
  
 Программа также может содержать инструкции условной компиляции. Их можно отключать в исходном файле между инструкциями предыдущей последовательности.  
  
### <a name="option-statements"></a>Операторы Option  
 `Option`инструкции устанавливают правила заземления для последующего кода, помогая предотвратить синтаксические и логические ошибки. [Оператор Option Explicit](../../language-reference/statements/option-explicit-statement.md) гарантирует, что все переменные объявляются и написаны правильно, что сокращает время отладки. [Оператор Option-Statement](../../language-reference/statements/option-strict-statement.md) позволяет снизить количество логических ошибок и потери данных, которые могут возникать при работе между переменными различных типов данных. [Оператор Option Compare](../../language-reference/statements/option-compare-statement.md) указывает, каким образом строки сравниваются друг с другом на основе их `Binary` `Text` значений или.  
  
### <a name="imports-statements"></a>Операторы Imports  
 Можно включить [оператор Imports (пространство имен .NET и тип)](../../language-reference/statements/imports-statement-net-namespace-and-type.md) для импорта имен, определенных за пределами проекта. `Imports`Оператор позволяет коду ссылаться на классы и другие типы, определенные в импортированном пространстве имен, без необходимости уточнять их. Можно использовать столько `Imports` инструкций, сколько необходимо. Дополнительные сведения см. [в разделе ссылки и оператор Imports](references-and-the-imports-statement.md).  
  
### <a name="namespace-statements"></a>Операторы пространства имен  
 Пространства имен помогают организовывать и классифицировать программные элементы для простоты группирования и доступа. [Оператор Namespace](../../language-reference/statements/namespace-statement.md) используется для классификации следующих операторов в определенном пространстве имен. Дополнительные сведения см. в разделе [Пространства имен в Visual Basic](namespaces.md).  
  
### <a name="conditional-compilation-statements"></a>Операторы условной компиляции  
 Операторы условной компиляции могут находиться практически в любом месте исходного файла. Они приводят к включению или исключению частей кода во время компиляции в зависимости от определенных условий. Их также можно использовать для отладки приложения, так как условный код выполняется только в режиме отладки. Дополнительные сведения см. в разделе [условная компиляция](conditional-compilation.md).  
  
## <a name="namespace-level-programming-elements"></a>Элементы программирования уровня пространства имен  
 Классы, структуры и модули содержат весь код в исходном файле. Они представляют собой элементы *уровня пространства имен* , которые могут использоваться в пространстве имен или на уровне исходного файла. Они содержат объявления всех других программных элементов. Интерфейсы, которые определяют подписи элементов, но не предоставляют реализации, также отображаются на уровне модуля. Дополнительные сведения об элементах уровня модуля см. в следующих статьях:  
  
- [Оператор Class](../../language-reference/statements/class-statement.md)  
  
- [Оператор Structure](../../language-reference/statements/structure-statement.md)  
  
- [Оператор Module](../../language-reference/statements/module-statement.md)  
  
- [Оператор Interface](../../language-reference/statements/interface-statement.md)  
  
 Элементы данных на уровне пространства имен являются перечислениями и делегатами.  
  
## <a name="module-level-programming-elements"></a>Элементы программирования уровня модуля  
 Процедуры, операторы, свойства и события — это единственные элементы программирования, которые могут содержать исполняемый код (операторы, выполняющие действия во время выполнения). Они являются элементами *уровня модуля* программы. Дополнительные сведения об элементах уровня процедуры см. в следующих статьях:  
  
- [Оператор Function](../../language-reference/statements/function-statement.md)  
  
- [Оператор Sub](../../language-reference/statements/sub-statement.md)  
  
- [Declare Statement](../../language-reference/statements/declare-statement.md)  
  
- [Operator Statement](../../language-reference/statements/operator-statement.md)  
  
- [Property Statement](../../language-reference/statements/property-statement.md)  
  
- [Оператор Event](../../language-reference/statements/event-statement.md)  
  
 Элементы данных на уровне модуля — это переменные, константы, перечисления и делегаты.  
  
## <a name="procedure-level-programming-elements"></a>Элементы программирования на уровне процедур  
 Большая часть содержимого элементов *уровня процедуры* — это исполняемые операторы, которые составляют код времени выполнения программы. Весь исполняемый код должен быть в некоторой процедуре ( `Function` ,,,,,, `Sub` `Operator` `Get` `Set` `AddHandler` `RemoveHandler` , `RaiseEvent` ). Дополнительные сведения см. в разделе [Инструкции](../language-features/statements.md).  
  
 Элементы данных на уровне процедуры ограничены локальными переменными и константами.  
  
## <a name="the-main-procedure"></a>Основная процедура  
 `Main`Процедура является первым кодом, который выполняется при загрузке приложения. `Main`служит в качестве начальной точки и общего управления для приложения. Существует четыре вида `Main` :  
  
- `Sub Main()`  
  
- `Sub Main(ByVal cmdArgs() As String)`  
  
- `Function Main() As Integer`  
  
- `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 Наиболее распространенная часть этой процедуры — `Sub Main()` . Дополнительные сведения см. [в разделе Главная процедура в Visual Basic](main-procedure.md).  
  
## <a name="see-also"></a>См. также раздел

- [Процедура Main в Visual Basic](main-procedure.md)
- [Соглашения об именах Visual Basic](naming-conventions.md)
- [Ограничения в Visual Basic](limitations.md)
