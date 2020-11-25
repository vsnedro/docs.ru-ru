---
title: Перечисление CorErrorIfEmitOutOfOrder
ms.date: 03/30/2017
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
ms.openlocfilehash: 1d1b0cbb8be33f285b63e7353da973455e0fd752
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718856"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="451a8-102">Перечисление CorErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="451a8-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>

<span data-ttu-id="451a8-103">Содержит значения флагов, указывающие условия, при которых должно создаваться сообщение об ошибке при беспорядочном выводе метаданных.</span><span class="sxs-lookup"><span data-stu-id="451a8-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="451a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="451a8-104">Syntax</span></span>  
  
```cpp  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a><span data-ttu-id="451a8-105">Члены</span><span class="sxs-lookup"><span data-stu-id="451a8-105">Members</span></span>  
  
|<span data-ttu-id="451a8-106">Член</span><span class="sxs-lookup"><span data-stu-id="451a8-106">Member</span></span>|<span data-ttu-id="451a8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="451a8-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="451a8-108">Указывает поведение по умолчанию, при котором не создаются сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="451a8-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="451a8-109">Указывает, что компилятор не должен создавать сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="451a8-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="451a8-110">Указывает, что компилятор должен создать сообщение об ошибке, когда поле, свойство, событие, метод или параметр выдаются в неопределенном порядке.</span><span class="sxs-lookup"><span data-stu-id="451a8-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="451a8-111">Указывает, что компилятор должен создать сообщение об ошибке, если метод выдается не по порядку.</span><span class="sxs-lookup"><span data-stu-id="451a8-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="451a8-112">Указывает, что компилятор должен создать сообщение об ошибке, если поле выдается не по порядку.</span><span class="sxs-lookup"><span data-stu-id="451a8-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="451a8-113">Указывает, что компилятор должен создать сообщение об ошибке, если параметр выдается не по порядку.</span><span class="sxs-lookup"><span data-stu-id="451a8-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="451a8-114">Указывает, что компилятор должен создать сообщение об ошибке, если свойство выдается не по порядку.</span><span class="sxs-lookup"><span data-stu-id="451a8-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="451a8-115">Указывает, что компилятор должен создать сообщение об ошибке, если событие выдается не по порядку.</span><span class="sxs-lookup"><span data-stu-id="451a8-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="451a8-116">Требования</span><span class="sxs-lookup"><span data-stu-id="451a8-116">Requirements</span></span>  

 <span data-ttu-id="451a8-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="451a8-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="451a8-118">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="451a8-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="451a8-119">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="451a8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="451a8-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="451a8-120">See also</span></span>

- [<span data-ttu-id="451a8-121">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="451a8-121">Metadata Enumerations</span></span>](metadata-enumerations.md)
