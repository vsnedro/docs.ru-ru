---
title: -vbruntime
ms.date: 03/13/2018
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
ms.openlocfilehash: 31b719fb7e43cdd6ac44424b359999410dd608a5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403048"
---
# <a name="-vbruntime"></a>-vbruntime
Указывает, что компилятор должен выполнять компиляцию без ссылки на библиотеку времени выполнения Visual Basic или со ссылкой на конкретную библиотеку времени выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Аргументы  
 \-  
 Компиляция без ссылки на библиотеку среды выполнения Visual Basic.  
  
 \+  
 Компиляция со ссылкой на библиотеку среды выполнения Visual Basic.  
  
 \*  
 Компиляция без ссылки на библиотеку среды выполнения Visual Basic и внедрение основных функции из этой библиотеки в сборку.  
  
 `path`  
 Компиляция со ссылкой на определенную библиотеку (DLL).  
  
## <a name="remarks"></a>Примечания  
 Параметр компилятора `-vbruntime` позволяет указать, что компилятор должен выполнять компиляцию без ссылки на библиотеку среды выполнения Visual Basic. В таком случае ошибки или предупреждения записываются для строк кода или языковых конструкций, которые выполняют вызов к вспомогательной функции среды выполнения Visual Basic. (*Вспомогательная функция среды выполнения Visual Basic* — это функция, определенная в Microsoft.VisualBasic.dll, которая вызывается во время выполнения для реализации определенной семантики языка.)  
  
 Если параметр `-vbruntime+` не указан, поведение будет таким же, как и при указании параметра `-vbruntime`. Параметр `-vbruntime+` можно использовать для переопределения предыдущих параметров `-vbruntime`.  
  
 Большинство объектов с типом `My` недоступны при использовании параметра `-vbruntime-` или `-vbruntime:path`.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Реализация основных функций среды выполнения Visual Basic  
 Параметр `-vbruntime*` позволяет выполнять компиляцию без ссылки на библиотеку среды выполнения. Вместо этого основные функции из библиотеки среды выполнения Visual Basic внедряются в пользовательскую сборку. Этот параметр можно использовать, если приложение выполняется на платформах без среды выполнения Visual Basic.  
  
 Внедряются следующие элементы среды выполнения:  
  
- Класс <xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
- Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
- Метод <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
- Метод <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
- константа <xref:Microsoft.VisualBasic.Constants.vbBack>;  
  
- константа <xref:Microsoft.VisualBasic.Constants.vbCr>;  
  
- константа <xref:Microsoft.VisualBasic.Constants.vbCrLf>;  
  
- константа <xref:Microsoft.VisualBasic.Constants.vbFormFeed>;  
  
- константа <xref:Microsoft.VisualBasic.Constants.vbLf>;  
  
- константа <xref:Microsoft.VisualBasic.Constants.vbNewLine>;  
  
- константа <xref:Microsoft.VisualBasic.Constants.vbNullChar>;  
  
- константа <xref:Microsoft.VisualBasic.Constants.vbNullString>;  
  
- константа <xref:Microsoft.VisualBasic.Constants.vbTab>;  
  
- константа <xref:Microsoft.VisualBasic.Constants.vbVerticalTab>;  
  
- некоторые объекты с типом `My`.  
  
 Если компиляция выполняется с параметром `-vbruntime*` и код ссылается на элемент из библиотеки среды выполнения Visual Basic, который не внедрен в основные функции, компилятор возвращает ошибку, указывающую на недоступность элемента.  
  
## <a name="referencing-a-specified-library"></a>Использование ссылки на определенную библиотеку  
 Вы можете использовать аргумент `path` для компиляции со ссылкой на пользовательскую библиотеку среды выполнения вместо стандартной библиотеки среды выполнения Visual Basic.  
  
 Если в качестве значения аргумента `path` указан полный путь к библиотеке DLL, компилятор будет использовать этот файл как библиотеку среды выполнения. Если значение аргумента `path` не является полным путем к DLL, компилятор Visual Basic сначала выполнит поиск определенной библиотеки DLL в текущей папке. Затем он выполнит поиск в папке, которую вы указали с помощью параметра компилятора [-sdkpath](sdkpath.md). Если параметр компилятора `-sdkpath` не используется, компилятор выполнит поиск определенной библиотеки DLL в папке .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать параметр `-vbruntime` для компиляции со ссылкой на пользовательскую библиотеку.  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>См. также

- [Visual Basic Core — новый режим компиляции в Visual Studio 2010 с пакетом обновления 1 (SP1)](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
- [-sdkpath](sdkpath.md)
