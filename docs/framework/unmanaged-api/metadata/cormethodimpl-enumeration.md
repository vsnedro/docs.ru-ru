---
title: Перечисление CorMethodImpl
ms.date: 03/30/2017
api_name:
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
ms.openlocfilehash: 40e82997e58292a10f5e960cc9d9785d9ea8946a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676982"
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="8521d-102">Перечисление CorMethodImpl</span><span class="sxs-lookup"><span data-stu-id="8521d-102">CorMethodImpl Enumeration</span></span>

<span data-ttu-id="8521d-103">Содержит значения, описывающие возможности реализации метода.</span><span class="sxs-lookup"><span data-stu-id="8521d-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8521d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8521d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a><span data-ttu-id="8521d-105">Члены</span><span class="sxs-lookup"><span data-stu-id="8521d-105">Members</span></span>  
  
|<span data-ttu-id="8521d-106">Член</span><span class="sxs-lookup"><span data-stu-id="8521d-106">Member</span></span>|<span data-ttu-id="8521d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8521d-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="8521d-108">Флаги, описывающие тип кода.</span><span class="sxs-lookup"><span data-stu-id="8521d-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="8521d-109">Указывает, что реализация метода является промежуточным языком Майкрософт (MSIL).</span><span class="sxs-lookup"><span data-stu-id="8521d-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="8521d-110">Указывает, что для метода используется стандартная реализация.</span><span class="sxs-lookup"><span data-stu-id="8521d-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="8521d-111">Указывает, что реализация метода — OPIL.</span><span class="sxs-lookup"><span data-stu-id="8521d-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="8521d-112">Указывает, что реализация метода предоставляется средой CLR.</span><span class="sxs-lookup"><span data-stu-id="8521d-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="8521d-113">Флаги, указывающие, является ли код управляемым или неуправляемым.</span><span class="sxs-lookup"><span data-stu-id="8521d-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="8521d-114">Указывает, что реализация метода является неуправляемой.</span><span class="sxs-lookup"><span data-stu-id="8521d-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="8521d-115">Указывает, что реализация метода является управляемой.</span><span class="sxs-lookup"><span data-stu-id="8521d-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="8521d-116">Указывает, что метод определен.</span><span class="sxs-lookup"><span data-stu-id="8521d-116">Specifies that the method is defined.</span></span> <span data-ttu-id="8521d-117">Этот флаг используется в основном в сценариях слияния.</span><span class="sxs-lookup"><span data-stu-id="8521d-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="8521d-118">Указывает, что подпись метода не может быть искажена для преобразования HRESULT.</span><span class="sxs-lookup"><span data-stu-id="8521d-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="8521d-119">Зарезервировано для внутреннего использования средой CLR.</span><span class="sxs-lookup"><span data-stu-id="8521d-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="8521d-120">Указывает, что метод является однопотоковым через его тело.</span><span class="sxs-lookup"><span data-stu-id="8521d-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="8521d-121">Указывает, что метод нельзя выполнять как встроенный.</span><span class="sxs-lookup"><span data-stu-id="8521d-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="8521d-122">Указывает, что метод должен быть встроенным, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="8521d-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="8521d-123">Указывает, что метод не должен быть оптимизирован.</span><span class="sxs-lookup"><span data-stu-id="8521d-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="8521d-124">Максимальное допустимое значение для `CorMethodImpl` .</span><span class="sxs-lookup"><span data-stu-id="8521d-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8521d-125">Требования</span><span class="sxs-lookup"><span data-stu-id="8521d-125">Requirements</span></span>  

 <span data-ttu-id="8521d-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8521d-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8521d-127">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="8521d-127">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8521d-128">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8521d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8521d-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8521d-129">See also</span></span>

- [<span data-ttu-id="8521d-130">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="8521d-130">Metadata Enumerations</span></span>](metadata-enumerations.md)
