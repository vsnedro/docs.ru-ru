---
title: Модуль<keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: 0cb009c22dada7b92956e113d33505923a92f2b3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362428"
---
# <a name="module-keyword-visual-basic"></a><span data-ttu-id="5e02f-102">Module \<keyword> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e02f-102">Module \<keyword> (Visual Basic)</span></span>
<span data-ttu-id="5e02f-103">Указывает, что атрибут в начале исходного файла применяется к текущему модулю сборки.</span><span class="sxs-lookup"><span data-stu-id="5e02f-103">Specifies that an attribute at the beginning of a source file applies to the current assembly module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e02f-104">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5e02f-104">Remarks</span></span>  
 <span data-ttu-id="5e02f-105">Многие атрибуты относятся к отдельному программному элементу, например классу или свойству.</span><span class="sxs-lookup"><span data-stu-id="5e02f-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="5e02f-106">Вы применяете такой атрибут, присоединив блок атрибута в угловых скобках ( `< >` ) непосредственно к оператору объявления.</span><span class="sxs-lookup"><span data-stu-id="5e02f-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="5e02f-107">Если атрибут относится не только к следующему элементу, но и к текущему модулю сборки, блок атрибута помещается в начало исходного файла и определяется атрибутом с `Module` ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="5e02f-107">If an attribute pertains not only to the following element but to the current assembly module, you place the attribute block at the beginning of the source file and identify the attribute with the `Module` keyword.</span></span> <span data-ttu-id="5e02f-108">Если он применяется ко всей сборке, используется ключевое слово [Assembly](assembly.md) .</span><span class="sxs-lookup"><span data-stu-id="5e02f-108">If it applies to the entire assembly, you use the [Assembly](assembly.md) keyword.</span></span>  
  
 <span data-ttu-id="5e02f-109">`Module`Модификатор не совпадает с [оператором module](../statements/module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5e02f-109">The `Module` modifier is not the same as the [Module Statement](../statements/module-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e02f-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5e02f-110">See also</span></span>

- [<span data-ttu-id="5e02f-111">Сборка</span><span class="sxs-lookup"><span data-stu-id="5e02f-111">Assembly</span></span>](assembly.md)
- [<span data-ttu-id="5e02f-112">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="5e02f-112">Module Statement</span></span>](../statements/module-statement.md)
- [<span data-ttu-id="5e02f-113">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="5e02f-113">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
