---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: c9bb302e2b34ebe1f51cf39bb3db1094d420d7f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408703"
---
# <a name="-delaysign"></a><span data-ttu-id="23a7f-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="23a7f-102">-delaysign</span></span>

<span data-ttu-id="23a7f-103">Указывает, будет ли сборка полностью или частично подписана.</span><span class="sxs-lookup"><span data-stu-id="23a7f-103">Specifies whether the assembly will be fully or partially signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="23a7f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23a7f-104">Syntax</span></span>

```console
-delaysign[+ | -]
```

## <a name="arguments"></a><span data-ttu-id="23a7f-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="23a7f-105">Arguments</span></span>

<span data-ttu-id="23a7f-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="23a7f-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="23a7f-107">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="23a7f-107">Optional.</span></span> <span data-ttu-id="23a7f-108">Если требуется полностью подписанная сборка, используйте `-delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="23a7f-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="23a7f-109">Используйте `-delaysign+`, если необходимо поместить открытый ключ в сборку и зарезервировать пространство для подписанного хэша.</span><span class="sxs-lookup"><span data-stu-id="23a7f-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="23a7f-110">Значение по умолчанию — `-delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="23a7f-110">The default is `-delaysign-`.</span></span>

## <a name="remarks"></a><span data-ttu-id="23a7f-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="23a7f-111">Remarks</span></span>

<span data-ttu-id="23a7f-112">Параметр `-delaysign` не имеет никакого эффекта, если вместе с ним не указан параметр [-keyfile](keyfile.md) или [-keycontainer](keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="23a7f-112">The `-delaysign` option has no effect unless used with [-keyfile](keyfile.md) or [-keycontainer](keycontainer.md).</span></span>

<span data-ttu-id="23a7f-113">При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки), и подписывает хэш закрытым ключом.</span><span class="sxs-lookup"><span data-stu-id="23a7f-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="23a7f-114">Итоговая цифровая подпись хранится в файле, содержащем манифест.</span><span class="sxs-lookup"><span data-stu-id="23a7f-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="23a7f-115">При использовании отложенной подписи компилятор не вычисляет и не сохраняет подпись, а резервирует место в файле для добавления подписи в сборку в будущем.</span><span class="sxs-lookup"><span data-stu-id="23a7f-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="23a7f-116">Например, с помощью `-delaysign+` разработчик в организации может распространять неподписанные тестовые версии сборки, которые тест-инженеры могут зарегистрировать в глобальном кэше сборок и впоследствии использовать.</span><span class="sxs-lookup"><span data-stu-id="23a7f-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="23a7f-117">После завершения работы над сборкой лицо, ответственное за закрытый ключ организации, может полностью подписать сборку.</span><span class="sxs-lookup"><span data-stu-id="23a7f-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="23a7f-118">Такая схема защищает закрытый ключ организации от раскрытия и при этом позволяет всем разработчикам работать со сборками.</span><span class="sxs-lookup"><span data-stu-id="23a7f-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>

<span data-ttu-id="23a7f-119">Дополнительные сведения см. в статье [Создание и использование сборок со строгими именами](../../../standard/assembly/create-use-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="23a7f-119">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>

### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="23a7f-120">Задание параметра -delaysign в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="23a7f-120">To set -delaysign in the Visual Studio integrated development environment</span></span>

1. <span data-ttu-id="23a7f-121">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="23a7f-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="23a7f-122">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="23a7f-122">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="23a7f-123">Откройте вкладку **Подписывание**.</span><span class="sxs-lookup"><span data-stu-id="23a7f-123">Click the **Signing** tab.</span></span>

3. <span data-ttu-id="23a7f-124">Задайте значение в поле **Только отложенная подпись**.</span><span class="sxs-lookup"><span data-stu-id="23a7f-124">Set the value in the **Delay sign only** box.</span></span>

## <a name="see-also"></a><span data-ttu-id="23a7f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="23a7f-125">See also</span></span>

- [<span data-ttu-id="23a7f-126">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="23a7f-126">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="23a7f-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="23a7f-127">-keyfile</span></span>](keyfile.md)
- [<span data-ttu-id="23a7f-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="23a7f-128">-keycontainer</span></span>](keycontainer.md)
- [<span data-ttu-id="23a7f-129">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="23a7f-129">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
