---
title: WriteOnly
ms.date: 07/20/2015
f1_keywords:
- WriteOnly
- vb.WriteOnly
helpviewer_keywords:
- write-only properties
- WriteOnly keyword [Visual Basic]
- sensitive data, protecting
- properties [Visual Basic], write-only
- sensitive data
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
ms.openlocfilehash: 12a1030a423359a3e4122eea98e223a1a02f680c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867624"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="99b30-102">WriteOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99b30-102">WriteOnly (Visual Basic)</span></span>

<span data-ttu-id="99b30-103">Указывает, что свойство может быть записано, но не прочитано.</span><span class="sxs-lookup"><span data-stu-id="99b30-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99b30-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="99b30-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="99b30-105">Правила</span><span class="sxs-lookup"><span data-stu-id="99b30-105">Rules</span></span>  

 <span data-ttu-id="99b30-106">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="99b30-106">**Declaration Context.**</span></span> <span data-ttu-id="99b30-107">`WriteOnly` можно использовать только на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="99b30-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="99b30-108">Это означает, что контекст объявления для `WriteOnly` свойства должен быть классом, структурой или модулем и не может быть исходным файлом, пространством имен или процедурой.</span><span class="sxs-lookup"><span data-stu-id="99b30-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="99b30-109">Можно объявить свойство как `WriteOnly` , но не переменную.</span><span class="sxs-lookup"><span data-stu-id="99b30-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="99b30-110">Когда следует использовать WriteOnly</span><span class="sxs-lookup"><span data-stu-id="99b30-110">When to Use WriteOnly</span></span>  

 <span data-ttu-id="99b30-111">Иногда требуется, чтобы в коде использовалась возможность задать значение, но не узнать, что это такое.</span><span class="sxs-lookup"><span data-stu-id="99b30-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="99b30-112">Например, конфиденциальные данные, например номер социальной регистрации или пароль, должны быть защищены от доступа любым компонентом, который не задал его.</span><span class="sxs-lookup"><span data-stu-id="99b30-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="99b30-113">В таких случаях `WriteOnly` для задания значения можно использовать свойство.</span><span class="sxs-lookup"><span data-stu-id="99b30-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="99b30-114">При определении и использовании `WriteOnly` Свойства учитывайте следующие дополнительные меры защиты:</span><span class="sxs-lookup"><span data-stu-id="99b30-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
- <span data-ttu-id="99b30-115">**Переопределение.**</span><span class="sxs-lookup"><span data-stu-id="99b30-115">**Overriding.**</span></span> <span data-ttu-id="99b30-116">Если свойство является членом класса, предоставьте ему значение по умолчанию [NotOverridable](notoverridable.md)и не объявляйте его `Overridable` или `MustOverride` .</span><span class="sxs-lookup"><span data-stu-id="99b30-116">If the property is a member of a class, allow it to default to [NotOverridable](notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="99b30-117">Это не позволяет производному классу делать нежелательный доступ с помощью переопределения.</span><span class="sxs-lookup"><span data-stu-id="99b30-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
- <span data-ttu-id="99b30-118">**Уровень доступа.**</span><span class="sxs-lookup"><span data-stu-id="99b30-118">**Access Level.**</span></span> <span data-ttu-id="99b30-119">Если конфиденциальные данные свойства хранятся в одной или нескольких переменных, объявите их [закрытыми](private.md) , чтобы другие коды не могли получить к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="99b30-119">If you hold the property's sensitive data in one or more variables, declare them [Private](private.md) so that no other code can access them.</span></span>  
  
- <span data-ttu-id="99b30-120">**Ключ.**</span><span class="sxs-lookup"><span data-stu-id="99b30-120">**Encryption.**</span></span> <span data-ttu-id="99b30-121">Храните все конфиденциальные данные в зашифрованном виде, а не в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="99b30-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="99b30-122">Если вредоносный код каким-либо образом получает доступ к этой области памяти, более сложно использовать эти данные.</span><span class="sxs-lookup"><span data-stu-id="99b30-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="99b30-123">Шифрование также полезно, если необходимо сериализовать конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="99b30-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
- <span data-ttu-id="99b30-124">**Сброс.**</span><span class="sxs-lookup"><span data-stu-id="99b30-124">**Resetting.**</span></span> <span data-ttu-id="99b30-125">При завершении работы класса, структуры или модуля, определяющего свойство, необходимо сбросить конфиденциальные данные на значения по умолчанию или другие бессмысленные значения.</span><span class="sxs-lookup"><span data-stu-id="99b30-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="99b30-126">Это обеспечивает дополнительную защиту при освобождении области памяти для общего доступа.</span><span class="sxs-lookup"><span data-stu-id="99b30-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
- <span data-ttu-id="99b30-127">**Сохраняемости.**</span><span class="sxs-lookup"><span data-stu-id="99b30-127">**Persistence.**</span></span> <span data-ttu-id="99b30-128">Не следует сохранять конфиденциальные данные, например на диске, если это можно избежать.</span><span class="sxs-lookup"><span data-stu-id="99b30-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="99b30-129">Кроме того, не записывайте конфиденциальные данные в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="99b30-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="99b30-130">`WriteOnly`Модификатор можно использовать в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="99b30-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="99b30-131">Property Statement</span><span class="sxs-lookup"><span data-stu-id="99b30-131">Property Statement</span></span>](../statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="99b30-132">См. также</span><span class="sxs-lookup"><span data-stu-id="99b30-132">See also</span></span>

- [<span data-ttu-id="99b30-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="99b30-133">ReadOnly</span></span>](readonly.md)
- [<span data-ttu-id="99b30-134">Частная</span><span class="sxs-lookup"><span data-stu-id="99b30-134">Private</span></span>](private.md)
- [<span data-ttu-id="99b30-135">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="99b30-135">Keywords</span></span>](../keywords/index.md)
