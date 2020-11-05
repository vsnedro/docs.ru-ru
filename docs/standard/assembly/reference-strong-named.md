---
title: Практическое руководство. Ссылка на сборку со строгим именем
description: В этой статье показано, как создавать ссылки на типы или ресурсы в сборке .NET со строгим именем во время компиляции или выполнения.
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 478f786995cfc4b57f0b18b2159775db104e9cfb
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687691"
---
# <a name="how-to-reference-a-strong-named-assembly"></a><span data-ttu-id="c4f4f-103">Практическое руководство. Ссылка на сборку со строгим именем</span><span class="sxs-lookup"><span data-stu-id="c4f4f-103">How to: Reference a strong-named assembly</span></span>
<span data-ttu-id="c4f4f-104">Процесс использования ссылок на типы или ресурсы, находящиеся в сборке со строгим именем, обычно понятен.</span><span class="sxs-lookup"><span data-stu-id="c4f4f-104">The process for referencing types or resources in a strong-named assembly is usually transparent.</span></span> <span data-ttu-id="c4f4f-105">Создать ссылку можно в момент компиляции (ранняя привязка) или же во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c4f4f-105">You can make the reference either at compile time (early binding) or at run time.</span></span>  
  
<span data-ttu-id="c4f4f-106">Во время компиляции создание ссылки происходит, когда компилятору указывается, что компилируемая сборка явно ссылается на другую сборку.</span><span class="sxs-lookup"><span data-stu-id="c4f4f-106">A compile-time reference occurs when you indicate to the compiler that the assembly to be compiled explicitly references another assembly.</span></span> <span data-ttu-id="c4f4f-107">При создании ссылок в момент компиляции компилятор автоматически получает открытый ключ нужной сборки со строгим именем и помещает его в ссылку компилируемой сборки.</span><span class="sxs-lookup"><span data-stu-id="c4f4f-107">When you use compile-time referencing, the compiler automatically gets the public key of the targeted strong-named assembly and places it in the assembly reference of the assembly being compiled.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c4f4f-108">Сборка со строгими именами может использовать только типы из других сборок со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="c4f4f-108">A strong-named assembly can only use types from other strong-named assemblies.</span></span> <span data-ttu-id="c4f4f-109">В противном случае нарушается безопасность сборки со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="c4f4f-109">Otherwise, the security of the strong-named assembly would be compromised.</span></span>  
  
## <a name="make-a-compile-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="c4f4f-110">Создание ссылки на сборку со строгим именем во время компиляции</span><span class="sxs-lookup"><span data-stu-id="c4f4f-110">Make a compile-time reference to a strong-named assembly</span></span>  

<span data-ttu-id="c4f4f-111">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c4f4f-111">At a command prompt, type the following command:</span></span>  

<span data-ttu-id="c4f4f-112">\<*compiler command*> **/reference:** \<*assembly name*></span><span class="sxs-lookup"><span data-stu-id="c4f4f-112">\<*compiler command*> **/reference:**\<*assembly name*></span></span>  

<span data-ttu-id="c4f4f-113">В этой команде *команда компилятора*  — команда компилятора для используемого языка, а *имя сборки*  — строгое имя сборки, на которую создается ссылка.</span><span class="sxs-lookup"><span data-stu-id="c4f4f-113">In this command, *compiler command* is the compiler command for the language you are using, and *assembly name* is the name of the strong-named assembly being referenced.</span></span> <span data-ttu-id="c4f4f-114">Кроме того, для создания сборки библиотеки можно использовать другие параметры компилятора, такие как **/t:library**.</span><span class="sxs-lookup"><span data-stu-id="c4f4f-114">You can also use other compiler options, such as the **/t:library** option for creating a library assembly.</span></span>  

<span data-ttu-id="c4f4f-115">В следующем примере показано создание сборки с именем *myAssembly.dll* , которая ссылается на сборку со строгим именем *myLibAssembly.dll* из модуля кода *myAssembly.cs*.</span><span class="sxs-lookup"><span data-stu-id="c4f4f-115">The following example creates an assembly called *myAssembly.dll* that references a strong-named assembly called *myLibAssembly.dll* from a code module called *myAssembly.cs*.</span></span>  

```cmd
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  

## <a name="make-a-run-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="c4f4f-116">Создание ссылки на сборку со строгим именем во время выполнения</span><span class="sxs-lookup"><span data-stu-id="c4f4f-116">Make a run-time reference to a strong-named assembly</span></span>  
  
<span data-ttu-id="c4f4f-117">Если вы создаете ссылку на сборку со строгим именем во время выполнения (например, с помощью метода <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> или <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>), нужно использовать отображаемое имя сборки со строгим именем, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="c4f4f-117">When you make a run-time reference to a strong-named assembly, for example by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> method, you must use the display name of the referenced strong-named assembly.</span></span> <span data-ttu-id="c4f4f-118">Отображаемое имя имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c4f4f-118">The syntax of a display name is as follows:</span></span>  

<span data-ttu-id="c4f4f-119">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span><span class="sxs-lookup"><span data-stu-id="c4f4f-119">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span></span>  

<span data-ttu-id="c4f4f-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="c4f4f-120">For example:</span></span>  

```console
myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33
```  

<span data-ttu-id="c4f4f-121">В этом примере `PublicKeyToken` представляет собой шестнадцатеричную форму маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="c4f4f-121">In this example, `PublicKeyToken` is the hexadecimal form of the public key token.</span></span> <span data-ttu-id="c4f4f-122">Если значение языка и региональных параметров отсутствует, используйте `Culture=neutral`.</span><span class="sxs-lookup"><span data-stu-id="c4f4f-122">If there is no culture value, use `Culture=neutral`.</span></span>  

<span data-ttu-id="c4f4f-123">В следующем примере кода показано использование этих данных с помощью метода <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c4f4f-123">The following code example shows how to use this information with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>  

```cpp
Assembly^ myDll =
    Assembly::Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```csharp
Assembly myDll =
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```vb
Dim myDll As Assembly = _
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1")
```

<span data-ttu-id="c4f4f-124">Распечатать в шестнадцатеричном формате открытый ключ и токен открытого ключа для определенной сборки можно с помощью следующей команды [строгого имени (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md):</span><span class="sxs-lookup"><span data-stu-id="c4f4f-124">You can print the hexadecimal format of the public key and public key token for a specific assembly by using the following [Strong Name (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) command:</span></span>  

<span data-ttu-id="c4f4f-125">**sn -Tp \<** *assembly* **>**</span><span class="sxs-lookup"><span data-stu-id="c4f4f-125">**sn -Tp \<** *assembly* **>**</span></span>  

<span data-ttu-id="c4f4f-126">Если же имеется файл открытого ключа, то вместо этого можно использовать следующую команду (обратите внимание на разный регистр символов в параметре командной строки):</span><span class="sxs-lookup"><span data-stu-id="c4f4f-126">If you have a public key file, you can use the following command instead (note the difference in case on the command-line option):</span></span>  

<span data-ttu-id="c4f4f-127">**sn -tp \<** *public key file* **>**</span><span class="sxs-lookup"><span data-stu-id="c4f4f-127">**sn -tp \<** *public key file* **>**</span></span>  

## <a name="see-also"></a><span data-ttu-id="c4f4f-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c4f4f-128">See also</span></span>

- [<span data-ttu-id="c4f4f-129">Создание и использование сборок со строгими именами</span><span class="sxs-lookup"><span data-stu-id="c4f4f-129">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
