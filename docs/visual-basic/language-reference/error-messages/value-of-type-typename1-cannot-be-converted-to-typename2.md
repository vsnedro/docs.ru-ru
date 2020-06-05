---
title: Значение типа <typename1> невозможно привести к <typename2>
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: f6b35efbc445887c537b94dd299b317a28e5f689
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406564"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2"></a><span data-ttu-id="ed3f3-102">Значение типа \<typename1> невозможно привести к \<typename2></span><span class="sxs-lookup"><span data-stu-id="ed3f3-102">Value of type '\<typename1>' cannot be converted to '\<typename2>'</span></span>
<span data-ttu-id="ed3f3-103">Значение типа " \<typename1> " не может быть преобразовано в " \<typename2> ".</span><span class="sxs-lookup"><span data-stu-id="ed3f3-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="ed3f3-104">Несоответствие типов может быть вызвано смешением ссылки на файл со ссылкой проекта на сборку " \<assemblyname> ".</span><span class="sxs-lookup"><span data-stu-id="ed3f3-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="ed3f3-105">Попробуйте заменить ссылку на файл " \<filepath> " в проекте " \<projectname1> " ссылкой проекта на " \<projectname2> ".</span><span class="sxs-lookup"><span data-stu-id="ed3f3-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="ed3f3-106">В ситуации, когда проект делает ссылку на проект и ссылку на файл, компилятор не может гарантировать, что один тип можно преобразовать в другой.</span><span class="sxs-lookup"><span data-stu-id="ed3f3-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="ed3f3-107">В следующем псевдо-коде показана ситуация, которая может вызвать эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="ed3f3-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 <span data-ttu-id="ed3f3-108">Project `P1` делает косвенную ссылку на проект через проект `P2` `P3` , а также прямую ссылку на файл `P3` .</span><span class="sxs-lookup"><span data-stu-id="ed3f3-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="ed3f3-109">В объявлении `commonObject` используется ссылка на файл `P3` , а в вызове `P2.getCommonClass` используется ссылка на проект `P3` .</span><span class="sxs-lookup"><span data-stu-id="ed3f3-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="ed3f3-110">Проблема в этой ситуации заключается в том, что ссылка на файл указывает путь к файлу и имя выходного файла `P3` (обычно P3. dll), а ссылки проекта определяют исходный проект ( `P3` ) по имени проекта.</span><span class="sxs-lookup"><span data-stu-id="ed3f3-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="ed3f3-111">По этой причине компилятор не может гарантировать, что тип `P3.commonClass` поступает из одного и того же исходного кода через две разные ссылки.</span><span class="sxs-lookup"><span data-stu-id="ed3f3-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="ed3f3-112">Эта ситуация обычно возникает, если ссылки на проект и ссылки на файлы являются смешанными.</span><span class="sxs-lookup"><span data-stu-id="ed3f3-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="ed3f3-113">На предыдущем рисунке проблема не возникнет, если `P1` сделать прямую ссылку на проект `P3` вместо ссылки на файл.</span><span class="sxs-lookup"><span data-stu-id="ed3f3-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="ed3f3-114">**Идентификатор ошибки:** BC30955</span><span class="sxs-lookup"><span data-stu-id="ed3f3-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ed3f3-115">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ed3f3-115">To correct this error</span></span>  
  
- <span data-ttu-id="ed3f3-116">Измените ссылку на файл на ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="ed3f3-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed3f3-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ed3f3-117">See also</span></span>

- [<span data-ttu-id="ed3f3-118">Преобразование типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ed3f3-118">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="ed3f3-119">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="ed3f3-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
