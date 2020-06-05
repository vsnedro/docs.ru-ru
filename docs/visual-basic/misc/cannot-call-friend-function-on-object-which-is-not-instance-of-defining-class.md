---
title: Невозможно вызвать дружественную функцию для объекта, не являющегося экземпляром определяющего класса.
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: c18c04470c4c49113e8195b92185326c5c4197c1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400852"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="4e0d7-102">Невозможно вызвать дружественную функцию для объекта, не являющегося экземпляром определяющего класса.</span><span class="sxs-lookup"><span data-stu-id="4e0d7-102">Cannot call friend function on object which is not an instance of defining class</span></span>
<span data-ttu-id="4e0d7-103">Предпринята попытка либо вызова процедуры `Friend` класса, либо получения доступа к дружественному ( `Friend` ) свойству или методу между процессами или между потоками.</span><span class="sxs-lookup"><span data-stu-id="4e0d7-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="4e0d7-104">Процедура `Friend` может вызываться из модуля вне класса, однако она является частью проекта, в котором определен класс.</span><span class="sxs-lookup"><span data-stu-id="4e0d7-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4e0d7-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4e0d7-105">To correct this error</span></span>  
  
- <span data-ttu-id="4e0d7-106">Убедитесь, что вызов процедуры или доступ к процедуре выполняется из модуля, являющегося частью проекта, в котором определен класс.</span><span class="sxs-lookup"><span data-stu-id="4e0d7-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e0d7-107">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4e0d7-107">See also</span></span>

- [<span data-ttu-id="4e0d7-108">Объявление</span><span class="sxs-lookup"><span data-stu-id="4e0d7-108">Friend</span></span>](../language-reference/modifiers/friend.md)
