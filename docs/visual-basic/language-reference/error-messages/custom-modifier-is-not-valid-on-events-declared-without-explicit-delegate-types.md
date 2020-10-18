---
title: Модификатор Custom недопустим для событий, объявленных без явных делегируемых типов
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: a2277e3778c2c252fd4b1eaeb033d549f041c15c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160637"
---
# <a name="bc31122-custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="35b2e-102">BC31122: Модификатор Custom недопустим для событий, объявленных без явных типов делегата</span><span class="sxs-lookup"><span data-stu-id="35b2e-102">BC31122: 'Custom' modifier is not valid on events declared without explicit delegate types</span></span>

<span data-ttu-id="35b2e-103">В отличие от нестандартного события, `Custom Event` объявление требует наличия `As` предложения, следующего за именем события, которое явно указывает тип делегата для события.</span><span class="sxs-lookup"><span data-stu-id="35b2e-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>

 <span data-ttu-id="35b2e-104">Ненастраиваемые события могут быть определены с помощью предложения, `As` явного типа делегата или списка параметров, непосредственно следующего за именем события.</span><span class="sxs-lookup"><span data-stu-id="35b2e-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>

 <span data-ttu-id="35b2e-105">**Идентификатор ошибки:** BC31122</span><span class="sxs-lookup"><span data-stu-id="35b2e-105">**Error ID:** BC31122</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="35b2e-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="35b2e-106">To correct this error</span></span>

1. <span data-ttu-id="35b2e-107">Определите делегат с тем же списком параметров, что и пользовательское событие.</span><span class="sxs-lookup"><span data-stu-id="35b2e-107">Define a delegate with the same parameter list as the custom event.</span></span>

     <span data-ttu-id="35b2e-108">Например, если объект `Custom Event` был определен с помощью `Custom Event Test(ByVal sender As Object, ByVal i As Integer)` , соответствующий делегат будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="35b2e-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>

     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]

2. <span data-ttu-id="35b2e-109">Замените список параметров пользовательского события `As` предложением с указанием типа делегата.</span><span class="sxs-lookup"><span data-stu-id="35b2e-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>

     <span data-ttu-id="35b2e-110">Продолжая работу с примером, `Custom Event` объявление будет перезаписано следующим образом.</span><span class="sxs-lookup"><span data-stu-id="35b2e-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>

     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]

## <a name="example"></a><span data-ttu-id="35b2e-111">Пример</span><span class="sxs-lookup"><span data-stu-id="35b2e-111">Example</span></span>

 <span data-ttu-id="35b2e-112">В этом примере объявляется `Custom Event` и указывается обязательное `As` предложение с типом делегата.</span><span class="sxs-lookup"><span data-stu-id="35b2e-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>

 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]

## <a name="see-also"></a><span data-ttu-id="35b2e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="35b2e-113">See also</span></span>

- [<span data-ttu-id="35b2e-114">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="35b2e-114">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="35b2e-115">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="35b2e-115">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="35b2e-116">События</span><span class="sxs-lookup"><span data-stu-id="35b2e-116">Events</span></span>](../../programming-guide/language-features/events/index.md)
