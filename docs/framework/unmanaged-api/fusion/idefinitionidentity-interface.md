---
title: Интерфейс IDefinitionIdentity
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
ms.openlocfilehash: 4f08fbbf9c8be16dff092327713e731c5aa14661
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732883"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="23dea-102">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="23dea-102">IDefinitionIdentity Interface</span></span>

<span data-ttu-id="23dea-103">Представляет уникальную сигнатуру кода, определяющего приложение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="23dea-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23dea-104">Методы</span><span class="sxs-lookup"><span data-stu-id="23dea-104">Methods</span></span>  
  
|<span data-ttu-id="23dea-105">Метод</span><span class="sxs-lookup"><span data-stu-id="23dea-105">Method</span></span>|<span data-ttu-id="23dea-106">Описание</span><span class="sxs-lookup"><span data-stu-id="23dea-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="23dea-107">Получает указатель интерфейса на новый `IDefinitionIdentity` объект, идентичный этому объекту `IDefinitionIdentity` , за исключением изменений указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="23dea-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="23dea-108">Возвращает указатель интерфейса на объект [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) , содержащий атрибуты, связанные с этим объектом `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="23dea-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="23dea-109">Возвращает значение атрибута с указанным именем в указанном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="23dea-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="23dea-110">Задает для атрибута с указанным именем в указанном пространстве имен указанное значение.</span><span class="sxs-lookup"><span data-stu-id="23dea-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23dea-111">Требования</span><span class="sxs-lookup"><span data-stu-id="23dea-111">Requirements</span></span>  

 <span data-ttu-id="23dea-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23dea-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23dea-113">**Заголовок:** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="23dea-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="23dea-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23dea-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23dea-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="23dea-115">See also</span></span>

- [<span data-ttu-id="23dea-116">Fusion-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="23dea-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
