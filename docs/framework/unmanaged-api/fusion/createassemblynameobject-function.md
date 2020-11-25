---
title: Функция CreateAssemblyNameObject
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
ms.openlocfilehash: 995f1064c2f40005c4a19ef034d7edfd668b5d51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704166"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="6b68b-102">Функция CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="6b68b-102">CreateAssemblyNameObject Function</span></span>

<span data-ttu-id="6b68b-103">Возвращает указатель интерфейса на экземпляр [IAssemblyName](iassemblyname-interface.md) , представляющий уникальный идентификатор сборки с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="6b68b-103">Gets an interface pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b68b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b68b-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b68b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6b68b-105">Parameters</span></span>  

 `ppAssemblyNameObj`  
 <span data-ttu-id="6b68b-106">заполняет Возвращаемое значение `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="6b68b-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="6b68b-107">окне Имя сборки, для которой создается новый `IAssemblyName` экземпляр.</span><span class="sxs-lookup"><span data-stu-id="6b68b-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6b68b-108">окне Флаги, передаваемые в конструктор объектов.</span><span class="sxs-lookup"><span data-stu-id="6b68b-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="6b68b-109">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="6b68b-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="6b68b-110">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="6b68b-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b68b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6b68b-111">Requirements</span></span>  

 <span data-ttu-id="6b68b-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b68b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b68b-113">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="6b68b-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6b68b-114">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6b68b-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6b68b-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b68b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b68b-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6b68b-116">See also</span></span>

- [<span data-ttu-id="6b68b-117">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="6b68b-117">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="6b68b-118">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="6b68b-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
