---
title: -refonly
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: b906178abf8d159083d95e41448596d512e857de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348579"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="fa436-102">-refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa436-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="fa436-103">Параметр **-refonly** указывает на то, что основными выходными данными должна быть базовая сборка, а не сборка реализации.</span><span class="sxs-lookup"><span data-stu-id="fa436-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="fa436-104">Параметр `-refonly` автоматически отключает вывод файлов PDB, так как базовые сборки не могут выполняться.</span><span class="sxs-lookup"><span data-stu-id="fa436-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="fa436-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa436-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="fa436-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="fa436-106">Remarks</span></span>

<span data-ttu-id="fa436-107">Поддержка параметра `-refonly` в Visual Basic появилась в версии 15.3.</span><span class="sxs-lookup"><span data-stu-id="fa436-107">Visual Basic supports the `-refonly` switch starting with version 15.3.</span></span>

<span data-ttu-id="fa436-108">Базовые сборки являются особым типом сборки, которая содержит только минимальный объем метаданных, необходимый для представления общедоступного API-интерфейса библиотеки.</span><span class="sxs-lookup"><span data-stu-id="fa436-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="fa436-109">Такие сборки включают в себя объявления для всех элементов, которые важны при указании ссылки на сборку в средствах сборки, но исключают все реализации элементов, а также объявления закрытых элементов, не имеющих наблюдаемого влияния на их контракт API.</span><span class="sxs-lookup"><span data-stu-id="fa436-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="fa436-110">Дополнительные сведения см. в разделе [Базовые сборки](../../../standard/assembly/reference-assemblies.md) в руководстве по .NET.</span><span class="sxs-lookup"><span data-stu-id="fa436-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="fa436-111">Параметры `-refonly` и [`-refout`](refout-compiler-option.md) являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="fa436-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa436-112">См. также</span><span class="sxs-lookup"><span data-stu-id="fa436-112">See also</span></span>

- [<span data-ttu-id="fa436-113">/refout</span><span class="sxs-lookup"><span data-stu-id="fa436-113">-refout</span></span>](refout-compiler-option.md)
- [<span data-ttu-id="fa436-114">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="fa436-114">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="fa436-115">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="fa436-115">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
