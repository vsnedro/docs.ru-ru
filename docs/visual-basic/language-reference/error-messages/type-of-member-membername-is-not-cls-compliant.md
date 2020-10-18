---
title: Тип члена <membername> не является CLS-совместимым
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: c8c14a2d6df8804967807af881384bc7d9ccd99f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163484"
---
# <a name="bc40025-type-of-member-membername-is-not-cls-compliant"></a><span data-ttu-id="0cc97-102">BC40025: тип члена "" несовместим с \<membername> CLS</span><span class="sxs-lookup"><span data-stu-id="0cc97-102">BC40025: Type of member '\<membername>' is not CLS-compliant</span></span>

<span data-ttu-id="0cc97-103">Тип данных, заданный для этого элемента, не входит в [независимость от языка и Language-Independent компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="0cc97-103">The data type specified for this member is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="0cc97-104">Это не ошибка в компоненте, так как .NET Framework и Visual Basic поддерживают этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="0cc97-104">This is not an error within your component, because the .NET Framework and Visual Basic support this data type.</span></span> <span data-ttu-id="0cc97-105">Однако другой компонент, написанный в строго CLS-совместимом коде, может не поддерживать этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="0cc97-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="0cc97-106">Такой компонент, возможно, не сможет успешно взаимодействовать с компонентом.</span><span class="sxs-lookup"><span data-stu-id="0cc97-106">Such a component might not be able to interact successfully with your component.</span></span>

 <span data-ttu-id="0cc97-107">Следующие типы данных Visual Basic несовместимы с CLS:</span><span class="sxs-lookup"><span data-stu-id="0cc97-107">The following Visual Basic data types are not CLS-compliant:</span></span>

- [<span data-ttu-id="0cc97-108">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="0cc97-108">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)

- [<span data-ttu-id="0cc97-109">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="0cc97-109">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)

- [<span data-ttu-id="0cc97-110">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="0cc97-110">ULong Data Type</span></span>](../data-types/ulong-data-type.md)

- [<span data-ttu-id="0cc97-111">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="0cc97-111">UShort Data Type</span></span>](../data-types/ushort-data-type.md)

 <span data-ttu-id="0cc97-112">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="0cc97-112">By default, this message is a warning.</span></span> <span data-ttu-id="0cc97-113">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="0cc97-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="0cc97-114">**Идентификатор ошибки:** BC40025</span><span class="sxs-lookup"><span data-stu-id="0cc97-114">**Error ID:** BC40025</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0cc97-115">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="0cc97-115">To correct this error</span></span>

- <span data-ttu-id="0cc97-116">Если компонент работает только с другими компонентами .NET Framework или не взаимодействует с другими компонентами, изменять ничего не нужно.</span><span class="sxs-lookup"><span data-stu-id="0cc97-116">If your component interfaces only with other .NET Framework components, or does not interface with any other components, you do not need to change anything.</span></span>

- <span data-ttu-id="0cc97-117">Если вы взаимодействуете с компонентом, не написанным для .NET Framework, вы можете определить, поддерживает ли этот тип данных либо с помощью отражения, либо из документации.</span><span class="sxs-lookup"><span data-stu-id="0cc97-117">If you are interfacing with a component not written for the .NET Framework, you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="0cc97-118">Если это так, вам не нужно ничего менять.</span><span class="sxs-lookup"><span data-stu-id="0cc97-118">If it does, you do not need to change anything.</span></span>

- <span data-ttu-id="0cc97-119">При взаимоработе с компонентом, который не поддерживает этот тип данных, необходимо заменить его ближайшим CLS-совместимым типом.</span><span class="sxs-lookup"><span data-stu-id="0cc97-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="0cc97-120">Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="0cc97-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="0cc97-121">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="0cc97-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>

- <span data-ttu-id="0cc97-122">При взаимоработе с автоматизацией или COM-объектами Помните, что некоторые типы имеют разную ширину данных, чем в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0cc97-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the .NET Framework.</span></span> <span data-ttu-id="0cc97-123">Например, данные типа `uint` часто являются 16-битными в других средах.</span><span class="sxs-lookup"><span data-stu-id="0cc97-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="0cc97-124">При передаче 16-разрядного аргумента в такой компонент объявите его как `UShort` вместо `UInteger` в управляемом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0cc97-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>

## <a name="see-also"></a><span data-ttu-id="0cc97-125">См. также</span><span class="sxs-lookup"><span data-stu-id="0cc97-125">See also</span></span>

- [<span data-ttu-id="0cc97-126">Отражение</span><span class="sxs-lookup"><span data-stu-id="0cc97-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
