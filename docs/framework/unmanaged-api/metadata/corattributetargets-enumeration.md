---
title: Перечисление CorAttributeTargets
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
ms.openlocfilehash: f1836f26af99f91ab1765107573f6b067edd5e95
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007927"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="d26dc-102">Перечисление CorAttributeTargets</span><span class="sxs-lookup"><span data-stu-id="d26dc-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="d26dc-103">Задает элементы приложения, в которых допустимо применять аргумент.</span><span class="sxs-lookup"><span data-stu-id="d26dc-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d26dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d26dc-104">Syntax</span></span>  
  
```cpp  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =
        catAssembly | catModule | catClass | catStruct |
        catEnum | catConstructor | catMethod | catProperty |
        catField | catEvent | catInterface | catParameter |
        catDelegate | catGenericParameter,  
  
    catClassMembers        =
        catClass | catStruct | catEnum | catConstructor |
        catMethod | catProperty | catField | catEvent |
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a><span data-ttu-id="d26dc-105">Участники</span><span class="sxs-lookup"><span data-stu-id="d26dc-105">Members</span></span>  
  
|<span data-ttu-id="d26dc-106">Член</span><span class="sxs-lookup"><span data-stu-id="d26dc-106">Member</span></span>|<span data-ttu-id="d26dc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d26dc-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="d26dc-108">Атрибут может быть применен к сборке.</span><span class="sxs-lookup"><span data-stu-id="d26dc-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="d26dc-109">Атрибут может применяться к переносимому исполняемому модулю (DLL или exe).</span><span class="sxs-lookup"><span data-stu-id="d26dc-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="d26dc-110">Атрибут может быть применен к классу.</span><span class="sxs-lookup"><span data-stu-id="d26dc-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="d26dc-111">Атрибут может быть применен к структуре, т.е. может являться типом значения.</span><span class="sxs-lookup"><span data-stu-id="d26dc-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="d26dc-112">Атрибут может быть применен к перечислению.</span><span class="sxs-lookup"><span data-stu-id="d26dc-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="d26dc-113">Атрибут может быть применен к конструктору.</span><span class="sxs-lookup"><span data-stu-id="d26dc-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="d26dc-114">Атрибут может быть применен к методу.</span><span class="sxs-lookup"><span data-stu-id="d26dc-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="d26dc-115">Атрибут может быть применен к свойству.</span><span class="sxs-lookup"><span data-stu-id="d26dc-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="d26dc-116">Атрибут может быть применен к полю.</span><span class="sxs-lookup"><span data-stu-id="d26dc-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="d26dc-117">Атрибут может быть применен к событию.</span><span class="sxs-lookup"><span data-stu-id="d26dc-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="d26dc-118">Атрибут может быть применен к интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="d26dc-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="d26dc-119">Атрибут может быть применен к параметру.</span><span class="sxs-lookup"><span data-stu-id="d26dc-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="d26dc-120">Атрибут может быть применен к делегату.</span><span class="sxs-lookup"><span data-stu-id="d26dc-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="d26dc-121">Атрибут может быть применен к универсальному параметру.</span><span class="sxs-lookup"><span data-stu-id="d26dc-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="d26dc-122">Атрибут может быть применен к любому элементу приложения.</span><span class="sxs-lookup"><span data-stu-id="d26dc-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="d26dc-123">Атрибут может применяться к члену класса.</span><span class="sxs-lookup"><span data-stu-id="d26dc-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d26dc-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="d26dc-124">Remarks</span></span>  
 <span data-ttu-id="d26dc-125">`CorAttributeTargets`Значения перечисления можно комбинировать с помощью битовой операции OR для получения предпочтительного сочетания.</span><span class="sxs-lookup"><span data-stu-id="d26dc-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="d26dc-126">Объект `CorAttributeTargets` параллельно управляет <xref:System.AttributeTargets?displayProperty=nameWithType> перечислением.</span><span class="sxs-lookup"><span data-stu-id="d26dc-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d26dc-127">Требования</span><span class="sxs-lookup"><span data-stu-id="d26dc-127">Requirements</span></span>  
 <span data-ttu-id="d26dc-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d26dc-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d26dc-129">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="d26dc-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d26dc-130">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d26dc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d26dc-131">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d26dc-131">See also</span></span>

- [<span data-ttu-id="d26dc-132">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="d26dc-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
