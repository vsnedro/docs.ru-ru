---
title: "Практическое руководство. Создание ссылки на сборку со строгим именем"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET Framework], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: aa46bfdfe42dca9509e39d4b6218473aa00a1877
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-reference-a-strong-named-assembly"></a><span data-ttu-id="74ee8-102">Практическое руководство. Создание ссылки на сборку со строгим именем</span><span class="sxs-lookup"><span data-stu-id="74ee8-102">How to: Reference a Strong-Named Assembly</span></span>
<span data-ttu-id="74ee8-103">Процесс использования ссылок на типы или ресурсы, находящиеся в сборке со строгим именем, обычно понятен.</span><span class="sxs-lookup"><span data-stu-id="74ee8-103">The process for referencing types or resources in a strong-named assembly is usually transparent.</span></span> <span data-ttu-id="74ee8-104">Создать ссылку можно в момент компиляции (ранняя привязка) или же во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="74ee8-104">You can make the reference either at compile time (early binding) or at run time.</span></span>  
  
 <span data-ttu-id="74ee8-105">Во время компиляции создание ссылки происходит, когда компилятору указывается, что текущая сборка явно ссылается на другую сборку.</span><span class="sxs-lookup"><span data-stu-id="74ee8-105">A compile-time reference occurs when you indicate to the compiler that your assembly explicitly references another assembly.</span></span> <span data-ttu-id="74ee8-106">При создании ссылок в момент компиляции компилятор автоматически получает открытый ключ нужной сборки со строгим именем и помещает его в ссылку компилируемой сборки.</span><span class="sxs-lookup"><span data-stu-id="74ee8-106">When you use compile-time referencing, the compiler automatically gets the public key of the targeted strong-named assembly and places it in the assembly reference of the assembly being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74ee8-107">Сборка со строгими именами может использовать только типы из других сборок со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="74ee8-107">A strong-named assembly can only use types from other strong-named assemblies.</span></span> <span data-ttu-id="74ee8-108">В противном случае нарушается безопасность сборки со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="74ee8-108">Otherwise, the security of the strong-named assembly would be compromised.</span></span>  
  
### <a name="to-make-a-compile-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="74ee8-109">Создание ссылки на сборку со строгим именем во время компиляции</span><span class="sxs-lookup"><span data-stu-id="74ee8-109">To make a compile-time reference to a strong-named assembly</span></span>  
  
1.  <span data-ttu-id="74ee8-110">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="74ee8-110">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="74ee8-111">\<*команда компилятора*> **/reference:**\<*имя сборки*></span><span class="sxs-lookup"><span data-stu-id="74ee8-111">\<*compiler command*> **/reference:**\<*assembly name*></span></span>  
  
     <span data-ttu-id="74ee8-112">В этой команде *команда компилятора* — команда компилятора для используемого языка, а *имя сборки* — строгое имя сборки, на которую создается ссылка.</span><span class="sxs-lookup"><span data-stu-id="74ee8-112">In this command, *compiler command* is the compiler command for the language you are using, and *assembly name* is the name of the strong-named assembly being referenced.</span></span> <span data-ttu-id="74ee8-113">Кроме того, для создания сборки библиотеки можно использовать другие параметры компилятора, такие как **/t:library**.</span><span class="sxs-lookup"><span data-stu-id="74ee8-113">You can also use other compiler options, such as the **/t:library** option for creating a library assembly.</span></span>  
  
 <span data-ttu-id="74ee8-114">В следующем примере показано создание сборки с именем `myAssembly.dll`, ссылается на сборку со строгим именем `myLibAssembly.dll` из модуля кода с именем `myAssembly.cs`.</span><span class="sxs-lookup"><span data-stu-id="74ee8-114">The following example creates an assembly called `myAssembly.dll` that references a strong-named assembly called `myLibAssembly.dll` from a code module called `myAssembly.cs`.</span></span>  
  
```  
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  
  
### <a name="to-make-a-run-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="74ee8-115">Создание ссылки на сборку со строгим именем во время выполнения</span><span class="sxs-lookup"><span data-stu-id="74ee8-115">To make a run-time reference to a strong-named assembly</span></span>  
  
1.  <span data-ttu-id="74ee8-116">Если вы создаете ссылку на сборку со строгим именем во время выполнения (например, с помощью метода <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> или <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName>), необходимо использовать отображаемое имя сборки со строгим именем, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="74ee8-116">When you make a run-time reference to a strong-named assembly (for example, by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> or <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> method), you must use the display name of the referenced strong-named assembly.</span></span> <span data-ttu-id="74ee8-117">Отображаемое имя имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="74ee8-117">The syntax of a display name is as follows:</span></span>  
  
     <span data-ttu-id="74ee8-118">\<*имя сборки*>**,** \<*номер версии*>**,** \<*язык и региональные параметры*>**,** \<*маркер открытого ключа*></span><span class="sxs-lookup"><span data-stu-id="74ee8-118">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span></span>  
  
     <span data-ttu-id="74ee8-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="74ee8-119">For example:</span></span>  
  
    ```  
    myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33   
    ```  
  
     <span data-ttu-id="74ee8-120">В этом примере `PublicKeyToken` представляет собой шестнадцатеричную форму маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="74ee8-120">In this example, `PublicKeyToken` is the hexadecimal form of the public key token.</span></span> <span data-ttu-id="74ee8-121">Если значение языка и региональных параметров отсутствует, используйте `Culture=neutral`.</span><span class="sxs-lookup"><span data-stu-id="74ee8-121">If there is no culture value, use `Culture=neutral`.</span></span>  
  
 <span data-ttu-id="74ee8-122">В следующем примере кода показано использование этих данных с помощью метода <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="74ee8-122">The following code example shows how to use this information with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="74ee8-123">[!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)] [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)] [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="74ee8-123">[!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)] [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)] [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]</span></span>  
  
 <span data-ttu-id="74ee8-124">Распечатать в шестнадцатеричном формате открытый ключ и токен открытого ключа для определенной сборки можно с помощью следующей команды [строгого имени (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md):</span><span class="sxs-lookup"><span data-stu-id="74ee8-124">You can print the hexadecimal format of the public key and public key token for a specific assembly by using the following [Strong Name (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) command:</span></span>  
  
 <span data-ttu-id="74ee8-125">**sn -Tp \<** *сборка* **>**</span><span class="sxs-lookup"><span data-stu-id="74ee8-125">**sn -Tp \<** *assembly* **>**</span></span>  
  
 <span data-ttu-id="74ee8-126">Если же имеется файл открытого ключа, то вместо этого можно использовать следующую команду (обратите внимание на разный регистр символов в параметре командной строки):</span><span class="sxs-lookup"><span data-stu-id="74ee8-126">If you have a public key file, you can use the following command instead (note the difference in case on the command-line option):</span></span>  
  
 <span data-ttu-id="74ee8-127">**sn -tp \<** *сборка* **>**</span><span class="sxs-lookup"><span data-stu-id="74ee8-127">**sn -tp \<** *assembly* **>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74ee8-128">См. также</span><span class="sxs-lookup"><span data-stu-id="74ee8-128">See Also</span></span>  
 [<span data-ttu-id="74ee8-129">Создание и использование сборок со строгими именами</span><span class="sxs-lookup"><span data-stu-id="74ee8-129">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
