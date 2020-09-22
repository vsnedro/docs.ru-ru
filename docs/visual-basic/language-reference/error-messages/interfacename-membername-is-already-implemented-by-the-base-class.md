---
title: <interfacename>.<membername> уже реализован базовым классом <baseclassname>. Предполагается повторная реализация <type>
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 4056c61bf6556f54276817c1c105ba7a17b6fd5a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873938"
---
# <a name="interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a><span data-ttu-id="2c146-103">\<interfacename>.\<membername> уже реализован базовым классом \<baseclassname>.</span><span class="sxs-lookup"><span data-stu-id="2c146-103">'\<interfacename>.\<membername>' is already implemented by the base class '\<baseclassname>'.</span></span> <span data-ttu-id="2c146-104">Предполагается повторная реализация \<type></span><span class="sxs-lookup"><span data-stu-id="2c146-104">Re-implementation of \<type> assumed</span></span>

<span data-ttu-id="2c146-105">Свойство, процедура или событие в производном классе использует `Implements` предложение, задающее член интерфейса, который уже реализован в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="2c146-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="2c146-106">Производный класс может повторно реализовать элемент интерфейса, который реализован его базовым классом.</span><span class="sxs-lookup"><span data-stu-id="2c146-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="2c146-107">Это не та же переопределяющая реализация базового класса.</span><span class="sxs-lookup"><span data-stu-id="2c146-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="2c146-108">Для получения дополнительной информации см. [Implements](../statements/implements-clause.md).</span><span class="sxs-lookup"><span data-stu-id="2c146-108">For more information, see [Implements](../statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="2c146-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="2c146-109">By default, this message is a warning.</span></span> <span data-ttu-id="2c146-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="2c146-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="2c146-111">**Идентификатор ошибки:** BC42015</span><span class="sxs-lookup"><span data-stu-id="2c146-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2c146-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2c146-112">To correct this error</span></span>  
  
- <span data-ttu-id="2c146-113">Если вы собираетесь реализовать элемент интерфейса, вам не нужно предпринимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2c146-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="2c146-114">Код в производном классе обращается к повторно реализованному элементу, если не используется `MyBase` ключевое слово для доступа к реализации базового класса.</span><span class="sxs-lookup"><span data-stu-id="2c146-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
- <span data-ttu-id="2c146-115">Если вы не собираетесь реализовать элемент интерфейса, удалите предложение `Implements` из свойства, процедуры или объявления события.</span><span class="sxs-lookup"><span data-stu-id="2c146-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c146-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2c146-116">See also</span></span>

- [<span data-ttu-id="2c146-117">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="2c146-117">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
