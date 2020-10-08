---
title: Wfc.exe (средство компилятора командной строки рабочего процесса)
description: Общие сведения о wfc.exe, средство компиляции командной строки рабочего процесса.
ms.date: 10/10/2020
helpviewer_keywords:
- wfc [Workflow]
- compiler tool
- wfc.exe
- Workflow, compilation
- Workflow, XOML files
- Workflow, wcf
ms.openlocfilehash: cf89962014584adf098118044b063b38b29160b7
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2020
ms.locfileid: "91844616"
---
# <a name="wfcexe-workflow-command-line-compiler-tool"></a>wfc.exe (средство компилятора командной строки рабочего процесса)
> [!NOTE]
> В этом материале обсуждаются устаревшие типы и пространства имен.

Средство компилятора командной строки рабочего процесса wfc.exe работает со старыми файлами разметки рабочих процессов с расширением *XOML* (устарело).

## <a name="compilation-process"></a>Процесс компиляции

При компиляции рабочих процессов выполняются указанные ниже процедуры.

- Выполняется проверка, гарантирующая, что действия рабочего процесса проверяются на основе правил, заданных действиями для самих себя. Если в процессе проверки возникают ошибки, компилятор возвращает список ошибок.  
- На основе разметки создается разделяемый класс, который подается на вход компилятора.  

- Создается код для запуска действий во время выполнения. Создаются подписки на события, оповещающие действия о завершении выполнения дочерних действий.  
- Разделяемые классы, созданные на основе файла разметки и файла кода, передаются компилятору .NET Framework для языка C# или Visual Basic. Выходные данные этого процесса — сборка .NET WorkflowSample.dll. Это можно развернуть для запуска рабочего процесса.

### <a name="compiler-options"></a>Параметры компилятора

В этом разделе показаны параметры для компилятора командной строки рабочего процесса wfc.exe.

```output
    Microsoft (R) Windows Workflow Compiler version 3.0.0.0
    Copyright (C) Microsoft Corporation 2005. All rights reserved.

                      Windows Workflow Compiler Options

    wfc.exe <Xoml file list> /target:assembly [<vb/cs file list>] [/language:...]
            [/out:...] [/reference:...] [/library:...] [/debug...] [/nocode...]
             [/checktypes...] [/resource:<resource info>]

                            - OUTPUT FILE -
    /out:<file>             Output file name
    /target:assembly        Build a Windows Workflow assembly (default).
                            Short form: /t:assembly
    /target:exe             Build a Windows Workflow application.
                            Short form: /t:exe
    /delaysign[+|-]         Delay-sign the assembly using only the public portion
                            of the strong name key.
    /keyfile:<file>         Specifies a strong name key file.
    /keycontainer:<string>  Specifies a strong name key container.

                            - INPUT FILES -
    <Xoml file list>        Xoml source file name(s).
    <vb/cs file list>       Code-beside file name(s).
    /reference:<file list>  Reference metadata from the specified assembly file(s).
                            Short form is '/r:'.
    /library:<path list>    Set of directories where to lookup for the references.
                            Short form is '/lib:'.
    /resource:<resinfo>     Embed the specified resource. Short form is '/res:'.
                            resinfo format is <file>[,<name>[,public|private]].

    Rules and freeform layout files must be embedded as assembly resources.
    The resource name is constructed by using the namespace and type name
    of the activity. For example, an activity named "MyActivity" in namespace
    "WFProject" would require resource names "WFProject.MyActivity.rules"
    and/or "WFProject.MyActivity.layout".

                            - CODE GENERATION -
    /debug[+|-]             Emit full debugging information. The default is '+'.
    /nocode[+|-]            Disallow code-beside model.
                            The default is '-'. Short form is '/nc:'.
    /checktypes[+|-]        Check for permitted types in wfc.exe.config file.
                            The default is '-'. Short form is '/ct:'.

                            - LANGUAGE -
    /language:[cs|vb]       The language to use for the generated class.
                            The default is 'CS' (C#). Short form is '/l:'.
    /rootnamespace:<string> Specifies the root Namespace for all type declarations.
                            Valid only for 'VB' (Visual Basic) language.
                            Short form is '/rns:'.

                            - MISCELLANEOUS -
    /help                   Display this usage message. Short form is '/?'.
    /nologo                 Suppress compiler copyright message. Short form is '/n'.

    /nowarn                 Ignore compiler warnings. Short form is '/w'.
```

## <a name="remarks"></a>Комментарии
> [!NOTE]
> В этом материале обсуждаются устаревшие типы и пространства имен.

Список разрешенных типов обычно определяется в файле *wfc.exe.config* . На этапе проверки компиляции рабочего процесса исходный документ рабочего процесса отклоняется, если он или сопутствующий файл правил непосредственно ссылается на любые типы .NET Framework, отсутствующие в списке разрешенных типов. Список разрешенных типов — это XML-документ, в котором каждая запись указывает на `Assembly` индикатор,,, `Namespace` `TypeName` и Полномочный элемент { `True`&#124;`False` }. `AuthorizedType` соответствует записи в списке. Допускаются подстановочные знаки, которые могут использоваться для включения или исключения полных пространств имен. Например, `Type="System.*"` включает все типы в <xref:System> , включая типы, содержащиеся в дочерних пространствах имен.
  
Использование списка разрешенных типов управляется <xref:System.Workflow.ComponentModel.Compiler.WorkflowCompiler> параметром `'/checktypes'` .

```xml  
<configuration>  
  <System.Workflow.ComponentModel.WorkflowCompiler>
    <authorizedTypes>
      <targetFx version="v4.0">
        ...
        <authorizedType Assembly="System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" Namespace="System*" TypeName="*" Authorized="True"/>
        ...
      </targetFx>
    </authorizedTypes>
  </System.Workflow.ComponentModel.WorkflowCompiler>  
</configuration>  
```

> [!WARNING]
> Если `Type="System.*"` тип существует, можно включить другие непредусмотренные типы, например `Type="System.Configuration"` , для компиляции. Следует соблюдать осторожность и проверять каждый из них. Для любого типа, который должен быть ограничен, обязательно задайте `Authorized` для значение `False` .

## <a name="see-also"></a>См. также

- [Класс Аусоризедтипе](xref:System.Workflow.ComponentModel.Compiler.AuthorizedType)
