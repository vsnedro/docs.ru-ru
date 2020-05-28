---
title: Метод IMetaDataEmit::DefineTypeRefByName
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
ms.openlocfilehash: ae30140e69926be32570960a32524a74b850bda4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009357"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="8ebef-102">Метод IMetaDataEmit::DefineTypeRefByName</span><span class="sxs-lookup"><span data-stu-id="8ebef-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="8ebef-103">Возвращает токен метаданных для типа, определенного в заданной области, которая находится за пределами текущей области.</span><span class="sxs-lookup"><span data-stu-id="8ebef-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ebef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ebef-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeRefByName (
    [in]  mdToken     tkResolutionScope,
    [in]  LPCWSTR     szName,
    [out] mdTypeRef   *ptr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ebef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8ebef-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="8ebef-106">окне Токен, указывающий область разрешения.</span><span class="sxs-lookup"><span data-stu-id="8ebef-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="8ebef-107">Допустимы следующие типы токенов:</span><span class="sxs-lookup"><span data-stu-id="8ebef-107">The following token types are valid:</span></span>  
  
- <span data-ttu-id="8ebef-108">`mdModuleRef`значение, если тип определен в той же сборке, в которой определен вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="8ebef-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
- <span data-ttu-id="8ebef-109">`mdAssemblyRef`значение, если тип определен в сборке, отличной от той, в которой определен вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="8ebef-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
- <span data-ttu-id="8ebef-110">`mdTypeRef`, если тип является вложенным типом.</span><span class="sxs-lookup"><span data-stu-id="8ebef-110">`mdTypeRef`, if the type is a nested type.</span></span>  
  
- <span data-ttu-id="8ebef-111">`mdModule`, если тип определен в том же модуле, в котором определен вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="8ebef-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
- <span data-ttu-id="8ebef-112">Значение null, если тип определен глобально.</span><span class="sxs-lookup"><span data-stu-id="8ebef-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="8ebef-113">окне Имя типа целевого объекта в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="8ebef-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="8ebef-114">заполняет Указатель на `mdTypeRef` токен, назначенный типу.</span><span class="sxs-lookup"><span data-stu-id="8ebef-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ebef-115">Требования</span><span class="sxs-lookup"><span data-stu-id="8ebef-115">Requirements</span></span>  
 <span data-ttu-id="8ebef-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ebef-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ebef-117">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="8ebef-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ebef-118">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8ebef-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ebef-119">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ebef-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ebef-120">См. также статью</span><span class="sxs-lookup"><span data-stu-id="8ebef-120">See also</span></span>

- [<span data-ttu-id="8ebef-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="8ebef-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8ebef-122">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="8ebef-122">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
