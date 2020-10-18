---
title: CLS-несовместимый <membername> не допускается в CLS-совместимом интерфейсе
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: aa7944e90857436553435ce783c0820770496a49
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159993"
---
# <a name="bc40033-non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="4b3bc-102">BC40033: несовместимый с CLS \<membername> не допускается в CLS-совместимом интерфейсе</span><span class="sxs-lookup"><span data-stu-id="4b3bc-102">BC40033: Non-CLS-compliant \<membername> is not allowed in a CLS-compliant interface</span></span>

<span data-ttu-id="4b3bc-103">Свойство, процедура или событие в интерфейсе помечается так, как `<CLSCompliant(True)>` если бы сам интерфейс был помечен как `<CLSCompliant(False)>` или, не помечен.</span><span class="sxs-lookup"><span data-stu-id="4b3bc-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>

 <span data-ttu-id="4b3bc-104">Для интерфейса, совместимого со [независимостьм от языка и Language-Independent компонентами](../../../standard/language-independence-and-language-independent-components.md) (CLS), все его члены должны соответствовать требованиям.</span><span class="sxs-lookup"><span data-stu-id="4b3bc-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>

 <span data-ttu-id="4b3bc-105">При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость.</span><span class="sxs-lookup"><span data-stu-id="4b3bc-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="4b3bc-106">Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.</span><span class="sxs-lookup"><span data-stu-id="4b3bc-106">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="4b3bc-107">Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.</span><span class="sxs-lookup"><span data-stu-id="4b3bc-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="4b3bc-108">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="4b3bc-108">By default, this message is a warning.</span></span> <span data-ttu-id="4b3bc-109">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4b3bc-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="4b3bc-110">**Идентификатор ошибки:** BC40033</span><span class="sxs-lookup"><span data-stu-id="4b3bc-110">**Error ID:** BC40033</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="4b3bc-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4b3bc-111">To correct this error</span></span>

- <span data-ttu-id="4b3bc-112">Если требуется обеспечить соответствие требованиям CLS и контролировать исходный код интерфейса, пометьте интерфейс как, `<CLSCompliant(True)>` Если все его члены соответствуют требованиям.</span><span class="sxs-lookup"><span data-stu-id="4b3bc-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>

- <span data-ttu-id="4b3bc-113">Если требуется CLS-совместимость и отсутствует контроль над исходным кодом интерфейса или если он не соответствует требованиям, определите этот член в другом интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="4b3bc-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>

- <span data-ttu-id="4b3bc-114">Если требуется, чтобы этот член оставался в текущем интерфейсе, удалите <xref:System.CLSCompliantAttribute> из его определения или пометьте его как `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="4b3bc-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b3bc-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4b3bc-115">See also</span></span>

- [<span data-ttu-id="4b3bc-116">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="4b3bc-116">Interface Statement</span></span>](../statements/interface-statement.md)
