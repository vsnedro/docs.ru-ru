---
title: Тип <typename> несовместим с CLS
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: eacf5036ebc6fc31dfa0e8de39c4fb574c9072b3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386962"
---
# <a name="type-typename-is-not-cls-compliant"></a><span data-ttu-id="29ae1-102">Тип \<typename> несовместим с CLS</span><span class="sxs-lookup"><span data-stu-id="29ae1-102">Type \<typename> is not CLS-compliant</span></span>
<span data-ttu-id="29ae1-103">Переменная, свойство или возвращаемое значение функции объявлены с типом данных, который не является CLS-совместимым.</span><span class="sxs-lookup"><span data-stu-id="29ae1-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="29ae1-104">Чтобы приложение было совместимо с [независимостьм от языка и независимыми от языка компонентами](../../../standard/language-independence-and-language-independent-components.md) (CLS), оно должно использовать только совместимые с CLS типы.</span><span class="sxs-lookup"><span data-stu-id="29ae1-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="29ae1-105">Следующие типы данных Visual Basic несовместимы с CLS:</span><span class="sxs-lookup"><span data-stu-id="29ae1-105">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="29ae1-106">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="29ae1-106">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="29ae1-107">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="29ae1-107">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="29ae1-108">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="29ae1-108">ULong Data Type</span></span>](../data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="29ae1-109">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="29ae1-109">UShort Data Type</span></span>](../data-types/ushort-data-type.md)  
  
 <span data-ttu-id="29ae1-110">**Идентификатор ошибки:** BC40041</span><span class="sxs-lookup"><span data-stu-id="29ae1-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="29ae1-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="29ae1-111">To correct this error</span></span>  
  
- <span data-ttu-id="29ae1-112">Если приложение должно быть совместимо с CLS, измените тип данных этого элемента на ближайший CLS-совместимый тип.</span><span class="sxs-lookup"><span data-stu-id="29ae1-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="29ae1-113">Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="29ae1-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="29ae1-114">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="29ae1-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="29ae1-115">Если приложение не обязательно должно быть CLS-совместимым, вам не нужно ничего менять.</span><span class="sxs-lookup"><span data-stu-id="29ae1-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="29ae1-116">Однако следует помнить о несоответствии.</span><span class="sxs-lookup"><span data-stu-id="29ae1-116">You should be aware of its noncompliance, however.</span></span>
