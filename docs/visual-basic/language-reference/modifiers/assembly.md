---
title: Сборка
ms.date: 07/20/2015
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
ms.openlocfilehash: 34d6b94f31336e3e99b8ca981a9c4899e5a3d912
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875521"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="1aaf4-102">Assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1aaf4-102">Assembly (Visual Basic)</span></span>

<span data-ttu-id="1aaf4-103">Указывает, что атрибут в начале исходного файла применяется ко всей сборке.</span><span class="sxs-lookup"><span data-stu-id="1aaf4-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1aaf4-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="1aaf4-104">Remarks</span></span>  

 <span data-ttu-id="1aaf4-105">Многие атрибуты относятся к отдельному программному элементу, например классу или свойству.</span><span class="sxs-lookup"><span data-stu-id="1aaf4-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="1aaf4-106">Вы применяете такой атрибут, присоединив блок атрибута в угловых скобках ( `< >` ) непосредственно к оператору объявления.</span><span class="sxs-lookup"><span data-stu-id="1aaf4-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="1aaf4-107">Если атрибут относится не только к следующему элементу, но и ко всей сборке, блок атрибута помещается в начало исходного файла и определяется атрибутом с `Assembly` ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="1aaf4-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="1aaf4-108">Если он применяется к текущему модулю сборки, используется ключевое слово [module](module-keyword.md) .</span><span class="sxs-lookup"><span data-stu-id="1aaf4-108">If it applies to the current assembly module, you use the [Module](module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="1aaf4-109">Можно также применить атрибут к сборке в файле AssemblyInfo. vb. в этом случае не нужно использовать блок атрибутов в основном файле исходного кода.</span><span class="sxs-lookup"><span data-stu-id="1aaf4-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aaf4-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1aaf4-110">See also</span></span>

- [<span data-ttu-id="1aaf4-111">Модуль \<keyword></span><span class="sxs-lookup"><span data-stu-id="1aaf4-111">Module \<keyword></span></span>](module-keyword.md)
- [<span data-ttu-id="1aaf4-112">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="1aaf4-112">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
