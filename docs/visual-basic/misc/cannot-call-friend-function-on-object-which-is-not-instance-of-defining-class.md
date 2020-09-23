---
title: Невозможно вызвать дружественную функцию для объекта, не являющегося экземпляром определяющего класса.
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: fe95f80d42fc12ab2829db899fe295e32f358db6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059812"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="4841d-102">Невозможно вызвать дружественную функцию для объекта, не являющегося экземпляром определяющего класса.</span><span class="sxs-lookup"><span data-stu-id="4841d-102">Cannot call friend function on object which is not an instance of defining class</span></span>

<span data-ttu-id="4841d-103">Предпринята попытка либо вызова процедуры `Friend` класса, либо получения доступа к дружественному ( `Friend` ) свойству или методу между процессами или между потоками.</span><span class="sxs-lookup"><span data-stu-id="4841d-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="4841d-104">Процедура `Friend` может вызываться из модуля вне класса, однако она является частью проекта, в котором определен класс.</span><span class="sxs-lookup"><span data-stu-id="4841d-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4841d-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4841d-105">To correct this error</span></span>  
  
- <span data-ttu-id="4841d-106">Убедитесь, что вызов процедуры или доступ к процедуре выполняется из модуля, являющегося частью проекта, в котором определен класс.</span><span class="sxs-lookup"><span data-stu-id="4841d-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4841d-107">См. также</span><span class="sxs-lookup"><span data-stu-id="4841d-107">See also</span></span>

- [<span data-ttu-id="4841d-108">Friend</span><span class="sxs-lookup"><span data-stu-id="4841d-108">Friend</span></span>](../language-reference/modifiers/friend.md)
