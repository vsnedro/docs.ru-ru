---
title: Имя <membername> не является CLS-совместимым
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 45c9332237dffc7311daeedaf36035d9e9958415
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397185"
---
# <a name="name-membername-is-not-cls-compliant"></a><span data-ttu-id="89a05-102">Имя \<membername> не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="89a05-102">Name \<membername> is not CLS-compliant</span></span>
<span data-ttu-id="89a05-103">Сборка помечается как, `<CLSCompliant(True)>` но предоставляет член с именем, которое начинается с символа подчеркивания ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="89a05-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="89a05-104">Программный элемент может содержать один или несколько символов подчеркивания, но для соответствия [языковым независимостьм и зависимым от языка компонентам](../../../standard/language-independence-and-language-independent-components.md) (CLS) он не должен начинаться с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="89a05-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="89a05-105">См. раздел [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="89a05-105">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="89a05-106">При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость.</span><span class="sxs-lookup"><span data-stu-id="89a05-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="89a05-107">Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.</span><span class="sxs-lookup"><span data-stu-id="89a05-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="89a05-108">Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.</span><span class="sxs-lookup"><span data-stu-id="89a05-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="89a05-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="89a05-109">By default, this message is a warning.</span></span> <span data-ttu-id="89a05-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="89a05-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="89a05-111">**Идентификатор ошибки:** BC40031</span><span class="sxs-lookup"><span data-stu-id="89a05-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="89a05-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="89a05-112">To correct this error</span></span>  
  
- <span data-ttu-id="89a05-113">Если вы управляете исходным кодом, измените его имя так, чтобы оно не начиналось с символа подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="89a05-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
- <span data-ttu-id="89a05-114">Если требуется, чтобы имя элемента оставалось без изменений, удалите <xref:System.CLSCompliantAttribute> из его определения или пометьте как `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="89a05-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="89a05-115">Вы по-прежнему можете пометить сборку как `<CLSCompliant(True)>` .</span><span class="sxs-lookup"><span data-stu-id="89a05-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a05-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="89a05-116">See also</span></span>

- [<span data-ttu-id="89a05-117">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="89a05-117">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="89a05-118">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="89a05-118">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
