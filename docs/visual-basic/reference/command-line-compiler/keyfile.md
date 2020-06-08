---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: 3f476f6b6db1a788002a938eb5ae4bbbed7a5dae
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408579"
---
# <a name="-keyfile"></a><span data-ttu-id="2e340-102">-keyfile</span><span class="sxs-lookup"><span data-stu-id="2e340-102">-keyfile</span></span>
<span data-ttu-id="2e340-103">Указывает файл, содержащий ключ или пару ключей, чтобы задать для сборки строгое имя.</span><span class="sxs-lookup"><span data-stu-id="2e340-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e340-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e340-104">Syntax</span></span>  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="2e340-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2e340-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="2e340-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="2e340-106">Required.</span></span> <span data-ttu-id="2e340-107">Файл, который содержит ключ.</span><span class="sxs-lookup"><span data-stu-id="2e340-107">File that contains the key.</span></span> <span data-ttu-id="2e340-108">Если имя файла содержит пробел, заключите это имя в кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="2e340-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e340-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="2e340-109">Remarks</span></span>  
 <span data-ttu-id="2e340-110">Компилятор вставляет открытый ключ в манифест сборки, а затем подписывает окончательную сборку закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="2e340-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="2e340-111">Чтобы создать файл ключа, в командной строке введите `sn -k file`.</span><span class="sxs-lookup"><span data-stu-id="2e340-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="2e340-112">Дополнительные сведения см. в статье [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2e340-112">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="2e340-113">При компиляции с параметром `-target:module` имя файла ключа сохраняется в модуле и включается в сборку, создаваемую при компиляции с параметром [-addmodule](addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="2e340-113">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](addmodule.md).</span></span>  
  
 <span data-ttu-id="2e340-114">Также можно передать сведения о шифровании компилятору с помощью параметра [-keycontainer](keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="2e340-114">You can also pass your encryption information to the compiler with [-keycontainer](keycontainer.md).</span></span> <span data-ttu-id="2e340-115">Если требуется использовать частично подписанную сборку, применяйте параметр [-delaysign](delaysign.md).</span><span class="sxs-lookup"><span data-stu-id="2e340-115">Use [-delaysign](delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="2e340-116">Этот параметр можно также указать в исходном коде любого модуля MSIL в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyFileAttribute>).</span><span class="sxs-lookup"><span data-stu-id="2e340-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="2e340-117">Если для одной процедуры компиляции одновременно заданы параметры `-keyfile` и [-keycontainer](keycontainer.md) (в командной строке или с помощью пользовательских атрибутов), то сначала компилятор пытается использовать контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="2e340-117">In case both `-keyfile` and [-keycontainer](keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="2e340-118">В случае успеха сборка подписывается данными контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="2e340-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="2e340-119">Если компилятору не удастся обнаружить контейнер ключей, будет предпринята попытка использовать файл, заданный параметром `-keyfile`.</span><span class="sxs-lookup"><span data-stu-id="2e340-119">If the compiler does not find the key container, it tries the file specified with `-keyfile`.</span></span> <span data-ttu-id="2e340-120">В случае успеха сборка подписывается данными из файла ключей, и эти данные о ключах помещаются в контейнер ключей (аналогично команде `sn -i`). Теперь при следующей компиляции контейнер ключей будет действителен.</span><span class="sxs-lookup"><span data-stu-id="2e340-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="2e340-121">Обратите внимание, что файл ключей может содержать только открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="2e340-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="2e340-122">Дополнительные сведения см. в статье [Создание и использование сборок со строгими именами](../../../standard/assembly/create-use-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="2e340-122">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e340-123">Параметр `-keyfile` недоступен в среде разработки Visual Studio. Он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="2e340-123">The `-keyfile` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="2e340-124">Пример</span><span class="sxs-lookup"><span data-stu-id="2e340-124">Example</span></span>

<span data-ttu-id="2e340-125">Следующий код компилирует `Input.vb` и определяет файл ключей.</span><span class="sxs-lookup"><span data-stu-id="2e340-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a><span data-ttu-id="2e340-126">См. также</span><span class="sxs-lookup"><span data-stu-id="2e340-126">See also</span></span>

- [<span data-ttu-id="2e340-127">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="2e340-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="2e340-128">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="2e340-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="2e340-129">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e340-129">-reference (Visual Basic)</span></span>](reference.md)
- [<span data-ttu-id="2e340-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="2e340-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
