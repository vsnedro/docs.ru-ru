---
title: Интерфейс IEnumIDENTITY_ATTRIBUTE
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
ms.openlocfilehash: 71a6ea9f593da093985a4420e690f1bdd7f9d139
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728996"
---
# <a name="ienumidentity_attribute-interface"></a><span data-ttu-id="f86e7-102">Интерфейс IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="f86e7-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>

<span data-ttu-id="f86e7-103">Служит в качестве перечислителя для атрибутов объекта Code в текущей области.</span><span class="sxs-lookup"><span data-stu-id="f86e7-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f86e7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f86e7-104">Methods</span></span>  
  
|<span data-ttu-id="f86e7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f86e7-105">Method</span></span>|<span data-ttu-id="f86e7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f86e7-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="f86e7-107">Возвращает указатель интерфейса на новый объект `IEnumIDENTITY_ATTRIBUTE` , содержащий те же элементы, что и этот объект `IEnumIDENTITY_ATTRIBUTE` .</span><span class="sxs-lookup"><span data-stu-id="f86e7-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="f86e7-108">Записывает данные, содержащиеся в элементах этого объекта `IEnumIDENTITY_ATTRIBUTE` , в указанный буфер данных.</span><span class="sxs-lookup"><span data-stu-id="f86e7-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="f86e7-109">Возвращает указанное число атрибутов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="f86e7-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="f86e7-110">Перемещает указатель инструкций в начало `IEnumIDENTITY_ATTRIBUTE` .</span><span class="sxs-lookup"><span data-stu-id="f86e7-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="f86e7-111">Перемещает указатель инструкции вперед на указанное число элементов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="f86e7-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f86e7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f86e7-112">Requirements</span></span>  

 <span data-ttu-id="f86e7-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f86e7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f86e7-114">**Заголовок:** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="f86e7-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="f86e7-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f86e7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f86e7-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f86e7-116">See also</span></span>

- [<span data-ttu-id="f86e7-117">Fusion-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="f86e7-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
