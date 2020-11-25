---
title: Метод IManagedObject::GetSerializedBuffer
ms.date: 03/30/2017
api_name:
- IManagedObject.GetSerializedBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type:
- apiref
ms.openlocfilehash: 159ece09ae0b6a67780639da8aae8c0e4b412bb8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730699"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="4e15c-102">Метод IManagedObject::GetSerializedBuffer</span><span class="sxs-lookup"><span data-stu-id="4e15c-102">IManagedObject::GetSerializedBuffer Method</span></span>

<span data-ttu-id="4e15c-103">Возвращает строковое представление этого управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="4e15c-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e15c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e15c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e15c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4e15c-105">Parameters</span></span>  

 `pBSTR`  
 <span data-ttu-id="4e15c-106">заполняет Указатель на строку, которая является сериализованным объектом.</span><span class="sxs-lookup"><span data-stu-id="4e15c-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e15c-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4e15c-107">Remarks</span></span>  

 <span data-ttu-id="4e15c-108">`GetSerializedBuffer`Метод сериализует объект, чтобы его можно было маршалировать клиенту.</span><span class="sxs-lookup"><span data-stu-id="4e15c-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e15c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4e15c-109">Requirements</span></span>  

 <span data-ttu-id="4e15c-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e15c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e15c-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4e15c-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e15c-112">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e15c-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e15c-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e15c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e15c-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4e15c-114">See also</span></span>

- [<span data-ttu-id="4e15c-115">Интерфейс IManagedObject</span><span class="sxs-lookup"><span data-stu-id="4e15c-115">IManagedObject Interface</span></span>](imanagedobject-interface.md)
