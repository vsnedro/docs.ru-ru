---
title: Значение типа <typename1> невозможно преобразовать в <typename2> (Множественные ссылки на файл)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 25008f05979638e050b74fc659fdc0a6d13b3c31
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406590"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2-multiple-file-references"></a><span data-ttu-id="c1a5c-102">Значение типа \<typename1> невозможно преобразовать в \<typename2> (Множественные ссылки на файл)</span><span class="sxs-lookup"><span data-stu-id="c1a5c-102">Value of type '\<typename1>' cannot be converted to '\<typename2>' (Multiple file references)</span></span>
<span data-ttu-id="c1a5c-103">Значение типа " \<typename1> " не может быть преобразовано в " \<typename2> ".</span><span class="sxs-lookup"><span data-stu-id="c1a5c-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="c1a5c-104">Несоответствие типов может быть вызвано смешением ссылки на файл " \<filepath1> " в проекте " \<projectname1> " со ссылкой на файл " \<filepath2> " в проекте " \<projectname2> ".</span><span class="sxs-lookup"><span data-stu-id="c1a5c-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="c1a5c-105">Если обе сборки идентичны, попробуйте заменить эти ссылки так, чтобы они ссылались из одного места.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="c1a5c-106">В ситуации, когда проект ссылается на сборку из нескольких файлов, компилятор не может гарантировать, что один тип можно преобразовать в другой.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="c1a5c-107">Каждая ссылка на файл указывает путь к файлу и имя выходного файла проекта (обычно это DLL-файл).</span><span class="sxs-lookup"><span data-stu-id="c1a5c-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="c1a5c-108">Компилятор не может гарантировать, что выходные файлы поступают из одного источника или что они представляют одну и ту же версию одной сборки.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="c1a5c-109">Поэтому он не может гарантировать, что типы в разных ссылках имеют одинаковый тип, или даже то, что один из них может быть преобразован в другой.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="c1a5c-110">Если известно, что упоминаемые сборки имеют одинаковое удостоверение сборки, можно использовать ссылку на один файл.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="c1a5c-111">*Удостоверение сборки* содержит имя сборки, версию, Открытый ключ, если таковые имеются, и язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="c1a5c-112">Эти сведения уникально идентифицируют сборку.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="c1a5c-113">**Идентификатор ошибки:** BC30961</span><span class="sxs-lookup"><span data-stu-id="c1a5c-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c1a5c-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c1a5c-114">To correct this error</span></span>  
  
- <span data-ttu-id="c1a5c-115">Если сборки, на которые имеются ссылки, имеют одинаковое удостоверение сборки, удалите или замените одну из ссылок на файлы, чтобы существовала только ссылка на один файл.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
- <span data-ttu-id="c1a5c-116">Если сборки, на которые имеются ссылки, не имеют одинакового идентификатора сборки, измените код таким образом, чтобы он не пытался преобразовать тип из одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a5c-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c1a5c-117">See also</span></span>

- [<span data-ttu-id="c1a5c-118">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c1a5c-118">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="c1a5c-119">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="c1a5c-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
