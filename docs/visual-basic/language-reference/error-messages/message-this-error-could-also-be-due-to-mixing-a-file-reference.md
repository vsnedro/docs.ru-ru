---
title: <message> Эта ошибка может также быть вызвана смешением ссылки на файл и ссылки проекта на сборку <assemblyname>
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: 263e30f992ef58b0053acb2fd749d0d9186ef6b8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397263"
---
# <a name="message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a><span data-ttu-id="5ea87-102">\<message> Эта ошибка может также быть вызвана смешением ссылки на файл и ссылки проекта на сборку \<assemblyname></span><span class="sxs-lookup"><span data-stu-id="5ea87-102">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>'</span></span>
<span data-ttu-id="5ea87-103">\<message>Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой проекта на сборку \<assemblyname> .</span><span class="sxs-lookup"><span data-stu-id="5ea87-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="5ea87-104">В этом случае попробуйте заменить ссылку на файл " \<assemblyfilename> " в проекте " \<projectname1> " ссылкой проекта на " \<projectname2> ".</span><span class="sxs-lookup"><span data-stu-id="5ea87-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="5ea87-105">Код в проекте обращается к члену другого проекта, но конфигурация решения не позволяет компилятору Visual Basic разрешить ссылку.</span><span class="sxs-lookup"><span data-stu-id="5ea87-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the Visual Basic compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="5ea87-106">Для доступа к типу, определенному в другой сборке, компилятор Visual Basic должен иметь ссылку на эту сборку.</span><span class="sxs-lookup"><span data-stu-id="5ea87-106">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="5ea87-107">Это должна быть одна однозначная ссылка, не вызывающая циклических ссылок между проектами.</span><span class="sxs-lookup"><span data-stu-id="5ea87-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="5ea87-108">**Идентификатор ошибки:** BC30971</span><span class="sxs-lookup"><span data-stu-id="5ea87-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5ea87-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="5ea87-109">To correct this error</span></span>  
  
1. <span data-ttu-id="5ea87-110">Определите, какой проект создает наиболее подходящую сборку для проекта, чтобы ссылаться на нее в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="5ea87-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="5ea87-111">Для этого можно использовать такие критерии, как простота доступа к файлам и частота обновления.</span><span class="sxs-lookup"><span data-stu-id="5ea87-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2. <span data-ttu-id="5ea87-112">В свойствах проекта добавьте ссылку на проект, содержащий сборку, определяющую используемый тип.</span><span class="sxs-lookup"><span data-stu-id="5ea87-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ea87-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5ea87-113">See also</span></span>

- [<span data-ttu-id="5ea87-114">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="5ea87-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="5ea87-115">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="5ea87-115">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="5ea87-116">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="5ea87-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="5ea87-117">Troubleshooting Broken References</span><span class="sxs-lookup"><span data-stu-id="5ea87-117">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
