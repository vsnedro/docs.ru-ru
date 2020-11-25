---
title: Перечисление CorCallingConvention
ms.date: 03/30/2017
api_name:
- CorCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallingConvention
helpviewer_keywords:
- CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type:
- apiref
ms.openlocfilehash: c9b20500a4a9e4649a938e00e3b059d1395da1d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718934"
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="16941-102">Перечисление CorCallingConvention</span><span class="sxs-lookup"><span data-stu-id="16941-102">CorCallingConvention Enumeration</span></span>

<span data-ttu-id="16941-103">Содержит значения, описывающие типы соглашений о вызовах, выполняемых в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="16941-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16941-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16941-104">Syntax</span></span>  
  
```cpp  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="16941-105">Члены</span><span class="sxs-lookup"><span data-stu-id="16941-105">Members</span></span>  
  
|<span data-ttu-id="16941-106">Член</span><span class="sxs-lookup"><span data-stu-id="16941-106">Member</span></span>|<span data-ttu-id="16941-107">Описание</span><span class="sxs-lookup"><span data-stu-id="16941-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="16941-108">Указывает соглашение о вызовах по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="16941-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="16941-109">Указывает, что метод принимает переменное число параметров.</span><span class="sxs-lookup"><span data-stu-id="16941-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="16941-110">Указывает, что вызов относится к полю.</span><span class="sxs-lookup"><span data-stu-id="16941-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="16941-111">Указывает, что вызов осуществляется в локальный метод.</span><span class="sxs-lookup"><span data-stu-id="16941-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="16941-112">Указывает, что вызов относится к свойству.</span><span class="sxs-lookup"><span data-stu-id="16941-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="16941-113">Указывает, что вызов является неуправляемым.</span><span class="sxs-lookup"><span data-stu-id="16941-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="16941-114">Указывает на создание экземпляра универсального метода.</span><span class="sxs-lookup"><span data-stu-id="16941-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="16941-115">Обозначает 64-разрядный вызов PInvoke для метода, принимающего переменное число параметров.</span><span class="sxs-lookup"><span data-stu-id="16941-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="16941-116">Описывает недопустимое 4-битовое значение.</span><span class="sxs-lookup"><span data-stu-id="16941-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="16941-117">Указывает, что соглашение о вызовах описывается четырьмя нижними битами.</span><span class="sxs-lookup"><span data-stu-id="16941-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="16941-118">Указывает, что верхний бит описывает `this` параметр.</span><span class="sxs-lookup"><span data-stu-id="16941-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="16941-119">Указывает, что `this` параметр явно описан в сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="16941-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="16941-120">Указывает сигнатуру универсального метода с явным числом аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="16941-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="16941-121">Это значение предшествует обычному числу параметров.</span><span class="sxs-lookup"><span data-stu-id="16941-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="16941-122">Требования</span><span class="sxs-lookup"><span data-stu-id="16941-122">Requirements</span></span>  

 <span data-ttu-id="16941-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16941-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16941-124">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="16941-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="16941-125">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16941-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16941-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="16941-126">See also</span></span>

- [<span data-ttu-id="16941-127">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="16941-127">Metadata Enumerations</span></span>](metadata-enumerations.md)
