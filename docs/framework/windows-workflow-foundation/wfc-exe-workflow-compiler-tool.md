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
ms.openlocfilehash: 01cbfeb72e19f727a3a470059047a2192228c394
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293862"
---
# <a name="wfcexe-workflow-command-line-compiler-tool"></a><span data-ttu-id="9a048-103">wfc.exe (средство компилятора командной строки рабочего процесса)</span><span class="sxs-lookup"><span data-stu-id="9a048-103">wfc.exe (Workflow Command-line Compiler Tool)</span></span>

> [!NOTE]
> <span data-ttu-id="9a048-104">В этом материале обсуждаются устаревшие типы и пространства имен.</span><span class="sxs-lookup"><span data-stu-id="9a048-104">This material discusses types and namespaces that are obsolete.</span></span>

<span data-ttu-id="9a048-105">Средство компилятора командной строки рабочего процесса wfc.exe работает со старыми файлами разметки рабочих процессов с расширением *XOML* (устарело).</span><span class="sxs-lookup"><span data-stu-id="9a048-105">The wfc.exe workflow command-line compiler tool works with old workflow markup files that have the file extension *.xoml* (obsoleted).</span></span>

## <a name="compilation-process"></a><span data-ttu-id="9a048-106">Процесс компиляции</span><span class="sxs-lookup"><span data-stu-id="9a048-106">Compilation process</span></span>

<span data-ttu-id="9a048-107">При компиляции рабочих процессов выполняются указанные ниже процедуры.</span><span class="sxs-lookup"><span data-stu-id="9a048-107">When workflows are compiled, the following procedures are performed as part of the compilation process:</span></span>

- <span data-ttu-id="9a048-108">Выполняется проверка, гарантирующая, что действия рабочего процесса проверяются на основе правил, заданных действиями для самих себя.</span><span class="sxs-lookup"><span data-stu-id="9a048-108">Validation is performed to ensure that the workflow activities validate based on the rules that the activities have set for themselves.</span></span> <span data-ttu-id="9a048-109">Если в процессе проверки возникают ошибки, компилятор возвращает список ошибок.</span><span class="sxs-lookup"><span data-stu-id="9a048-109">If there are validation errors, the compiler returns a list of the errors.</span></span>  
- <span data-ttu-id="9a048-110">На основе разметки создается разделяемый класс, который подается на вход компилятора.</span><span class="sxs-lookup"><span data-stu-id="9a048-110">A partial class is generated from the markup definition that is input into the compiler.</span></span>  

- <span data-ttu-id="9a048-111">Создается код для запуска действий во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9a048-111">Code is generated to help with the run-time execution of the activities.</span></span> <span data-ttu-id="9a048-112">Создаются подписки на события, оповещающие действия о завершении выполнения дочерних действий.</span><span class="sxs-lookup"><span data-stu-id="9a048-112">Event subscriptions are generated, which help activities know when the activities they contain are finished executing.</span></span>  
- <span data-ttu-id="9a048-113">Разделяемые классы, созданные на основе файла разметки и файла кода, передаются компилятору .NET Framework для языка C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9a048-113">The partial classes generated from the markup file and the partial classes from the code file are entered into the .NET Framework C# or Visual Basic compiler.</span></span> <span data-ttu-id="9a048-114">Выходные данные этого процесса — сборка .NET WorkflowSample.dll.</span><span class="sxs-lookup"><span data-stu-id="9a048-114">The output of this process is the .NET assembly, WorkflowSample.dll.</span></span> <span data-ttu-id="9a048-115">Это можно развернуть для запуска рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9a048-115">This can be deployed to run the workflow.</span></span>

### <a name="compiler-options"></a><span data-ttu-id="9a048-116">Параметры компилятора</span><span class="sxs-lookup"><span data-stu-id="9a048-116">Compiler options</span></span>

<span data-ttu-id="9a048-117">В этом разделе показаны параметры для компилятора командной строки рабочего процесса wfc.exe.</span><span class="sxs-lookup"><span data-stu-id="9a048-117">This section shows the options for the wfc.exe workflow command-line compiler.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="9a048-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="9a048-118">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="9a048-119">В этом материале обсуждаются устаревшие типы и пространства имен.</span><span class="sxs-lookup"><span data-stu-id="9a048-119">This material discusses types and namespaces that are obsolete.</span></span>

<span data-ttu-id="9a048-120">Список разрешенных типов обычно определяется в файле *wfc.exe.config* .</span><span class="sxs-lookup"><span data-stu-id="9a048-120">A list of authorized types is usually defined in the *wfc.exe.config* file.</span></span> <span data-ttu-id="9a048-121">На этапе проверки компиляции рабочего процесса исходный документ рабочего процесса отклоняется, если он или сопутствующий файл правил непосредственно ссылается на любые типы .NET Framework, отсутствующие в списке разрешенных типов.</span><span class="sxs-lookup"><span data-stu-id="9a048-121">During the validation phase of workflow compilation, a workflow source document is rejected if it or the companion rules file directly references any .NET Framework types not present in a list of authorized types.</span></span> <span data-ttu-id="9a048-122">Список разрешенных типов — это XML-документ, в котором каждая запись указывает на `Assembly` индикатор,,, `Namespace` `TypeName` и Полномочный элемент { `True`&#124;`False` }.</span><span class="sxs-lookup"><span data-stu-id="9a048-122">The list of authorized types is an XML document where each entry indicates an `Assembly`, a `Namespace`, a `TypeName`, and an Authorized {`True`&#124;`False`} indicator.</span></span> <span data-ttu-id="9a048-123">`AuthorizedType` соответствует записи в списке.</span><span class="sxs-lookup"><span data-stu-id="9a048-123">`AuthorizedType` corresponds to an entry in the list.</span></span> <span data-ttu-id="9a048-124">Допускаются подстановочные знаки, которые могут использоваться для включения или исключения полных пространств имен.</span><span class="sxs-lookup"><span data-stu-id="9a048-124">Wildcard character designations, which can be used to include or exclude complete namespaces, are allowed.</span></span> <span data-ttu-id="9a048-125">Например, `Type="System.*"` включает все типы в <xref:System> , включая типы, содержащиеся в дочерних пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="9a048-125">For example, `Type="System.*"` includes all types in <xref:System>, including types contained in child namespaces.</span></span>
  
<span data-ttu-id="9a048-126">Использование списка разрешенных типов управляется <xref:System.Workflow.ComponentModel.Compiler.WorkflowCompiler> параметром `'/checktypes'` .</span><span class="sxs-lookup"><span data-stu-id="9a048-126">The use of a list of authorized types is controlled by the <xref:System.Workflow.ComponentModel.Compiler.WorkflowCompiler> option `'/checktypes'`.</span></span>

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
> <span data-ttu-id="9a048-127">Если `Type="System.*"` тип существует, можно включить другие непредусмотренные типы, например `Type="System.Configuration"` , для компиляции.</span><span class="sxs-lookup"><span data-stu-id="9a048-127">When `Type="System.*"` type is present, it's possible to include other unintended types, such as `Type="System.Configuration"`, for compilation.</span></span> <span data-ttu-id="9a048-128">Следует соблюдать осторожность и проверять каждый из них.</span><span class="sxs-lookup"><span data-stu-id="9a048-128">You should be cautious and review each one.</span></span> <span data-ttu-id="9a048-129">Для любого типа, который должен быть ограничен, обязательно задайте `Authorized` для значение `False` .</span><span class="sxs-lookup"><span data-stu-id="9a048-129">For any type that should be restricted, be sure to set `Authorized` to `False`.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a048-130">См. также</span><span class="sxs-lookup"><span data-stu-id="9a048-130">See also</span></span>

- [<span data-ttu-id="9a048-131">Класс Аусоризедтипе</span><span class="sxs-lookup"><span data-stu-id="9a048-131">AuthorizedType class</span></span>](xref:System.Workflow.ComponentModel.Compiler.AuthorizedType)
