---
title: "Практическое руководство. Создание пары открытого и закрытого ключей"
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
- key pairs for strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- cryptographic key pairs
- snk files (key pair files)
- public-private key pairs
- .snk files
- strong-named assemblies, key pairs
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 772bcae9c3467553e4ca90989a82798155ee034c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-public-private-key-pair"></a><span data-ttu-id="41a9a-102">Практическое руководство. Создание пары открытого и закрытого ключей</span><span class="sxs-lookup"><span data-stu-id="41a9a-102">How to: Create a Public-Private Key Pair</span></span>
<span data-ttu-id="41a9a-103">Для подписи сборки строгим именем необходимо иметь пару, состоящую из открытого и закрытого ключа.</span><span class="sxs-lookup"><span data-stu-id="41a9a-103">To sign an assembly with a strong name, you must have a public/private key pair.</span></span> <span data-ttu-id="41a9a-104">Эта пара криптографических ключей используется во время компиляции для создания сборки со строгим именем.</span><span class="sxs-lookup"><span data-stu-id="41a9a-104">This public and private cryptographic key pair is used during compilation to create a strong-named assembly.</span></span> <span data-ttu-id="41a9a-105">Пару ключей можно создать с помощью [средства для работы со строгими именами (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="41a9a-105">You can create a key pair using the [Strong Name tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md).</span></span> <span data-ttu-id="41a9a-106">Файлы пары ключей обычно имеют расширение SNK.</span><span class="sxs-lookup"><span data-stu-id="41a9a-106">Key pair files usually have an .snk extension.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41a9a-107">В [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] страницы свойств проекта C# и Visual Basic включают вкладку **Подписание**, которая позволяет выбрать существующие файлы ключей или создать новые файлы ключей без использования Sn.exe.</span><span class="sxs-lookup"><span data-stu-id="41a9a-107">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], the C# and Visual Basic project property pages include a **Signing** tab that enables you to select existing key files or to generate new key files without using Sn.exe.</span></span> <span data-ttu-id="41a9a-108">В Visual C++ можно указать расположение уже существующего файла ключа на странице свойств **Дополнительно** в разделе **Компоновщик** раздела **Свойства конфигурации** окна **Страницы свойств**.</span><span class="sxs-lookup"><span data-stu-id="41a9a-108">In Visual C++, you can specify the location of an existing key file in the **Advanced** property page in the **Linker** section of the **Configuration Properties** section of the **Property Pages** window.</span></span> <span data-ttu-id="41a9a-109">Использование атрибута [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] для идентификации пар файлов ключей признано устаревшим, начиная с <xref:System.Reflection.AssemblyKeyFileAttribute>.</span><span class="sxs-lookup"><span data-stu-id="41a9a-109">The use of the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute to identify key file pairs has been made obsolete beginning with [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].</span></span>  
  
### <a name="to-create-a-key-pair"></a><span data-ttu-id="41a9a-110">Создание пары ключей</span><span class="sxs-lookup"><span data-stu-id="41a9a-110">To create a key pair</span></span>  
  
1.  <span data-ttu-id="41a9a-111">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="41a9a-111">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="41a9a-112">**sn –k** \<*имя файла*></span><span class="sxs-lookup"><span data-stu-id="41a9a-112">**sn –k** \<*file name*></span></span>  
  
     <span data-ttu-id="41a9a-113">В этой команде *имя файла* — это имя выходного файла, содержащего пару ключей.</span><span class="sxs-lookup"><span data-stu-id="41a9a-113">In this command, *file name* is the name of the output file containing the key pair.</span></span>  
  
 <span data-ttu-id="41a9a-114">В следующем примере создается пара ключей с именем `sgKey.snk`.</span><span class="sxs-lookup"><span data-stu-id="41a9a-114">The following example creates a key pair called `sgKey.snk`.</span></span>  
  
```  
sn -k sgKey.snk  
```  
  
 <span data-ttu-id="41a9a-115">Если требуется отложить подписание сборки, а также управлять парой ключей целиком (что может потребоваться разве что для тестирования), можно использовать следующие команды для создания пары ключей и извлечения открытого ключа из нее в отдельный файл.</span><span class="sxs-lookup"><span data-stu-id="41a9a-115">If you intend to delay sign an assembly and you control the whole key pair (which is unlikely outside test scenarios), you can use the following commands to generate a key pair and then extract the public key from it into a separate file.</span></span> <span data-ttu-id="41a9a-116">Во-первых, создайте пару ключей:</span><span class="sxs-lookup"><span data-stu-id="41a9a-116">First, create the key pair:</span></span>  
  
```  
sn -k keypair.snk  
```  
  
 <span data-ttu-id="41a9a-117">Затем извлеките открытый ключ из пары ключей и скопируйте его в отдельный файл:</span><span class="sxs-lookup"><span data-stu-id="41a9a-117">Next, extract the public key from the key pair and copy it to a separate file:</span></span>  
  
```  
sn -p keypair.snk public.snk  
```  
  
 <span data-ttu-id="41a9a-118">После создания пары ключей необходимо поместить файл в расположение, в котором его смогут найти инструменты создания подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="41a9a-118">Once you create the key pair, you must put the file where the strong name signing tools can find it.</span></span>  
  
 <span data-ttu-id="41a9a-119">При подписании сборки строгим именем [компоновщик сборок (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) выполняет поиск файла ключа относительно текущей и выходной папки.</span><span class="sxs-lookup"><span data-stu-id="41a9a-119">When signing an assembly with a strong name, the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) looks for the key file relative to the current directory and to the output directory.</span></span> <span data-ttu-id="41a9a-120">При использовании компиляторов, работающих в режиме командной строки, достаточно просто скопировать ключ в текущий каталог, содержащий модули кода.</span><span class="sxs-lookup"><span data-stu-id="41a9a-120">When using command-line compilers, you can simply copy the key to the current directory containing your code modules.</span></span>  
  
 <span data-ttu-id="41a9a-121">При использовании более ранней версии [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], в которой нет вкладки **Подписание** в свойствах проекта, рекомендуемым расположением файла ключа является каталог проекта с атрибутом файла, заданным следующим образом:</span><span class="sxs-lookup"><span data-stu-id="41a9a-121">If you are using an earlier version of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] that does not have a **Signing** tab in the project properties, the recommended key file location is the project directory with the file attribute specified as follows:</span></span>  
  
 <span data-ttu-id="41a9a-122">[!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)] [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)] [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]</span><span class="sxs-lookup"><span data-stu-id="41a9a-122">[!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)] [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)] [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a9a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="41a9a-123">See Also</span></span>  
 [<span data-ttu-id="41a9a-124">Создание и использование сборок со строгими именами</span><span class="sxs-lookup"><span data-stu-id="41a9a-124">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
