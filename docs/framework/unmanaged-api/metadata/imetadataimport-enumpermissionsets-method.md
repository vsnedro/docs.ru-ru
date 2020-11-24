---
title: Метод IMetaDataImport::EnumPermissionSets
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
ms.openlocfilehash: eef2c733f96d74e3353a940cc90f1a631cf48a36
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690529"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="87465-102">Метод IMetaDataImport::EnumPermissionSets</span><span class="sxs-lookup"><span data-stu-id="87465-102">IMetaDataImport::EnumPermissionSets Method</span></span>

<span data-ttu-id="87465-103">Перечисляет разрешения для объектов в указанной области метаданных.</span><span class="sxs-lookup"><span data-stu-id="87465-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87465-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87465-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,
   [in]      mdToken       tk,
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87465-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="87465-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="87465-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="87465-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="87465-107">При первом вызове этого метода это значение должно быть равно NULL.</span><span class="sxs-lookup"><span data-stu-id="87465-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="87465-108">окне Токен метаданных, ограничивающий область поиска, или значение NULL для поиска по самой широкой области.</span><span class="sxs-lookup"><span data-stu-id="87465-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="87465-109">окне Флаги, представляющие <xref:System.Security.Permissions.SecurityAction> значения, которые необходимо включить в `rPermission` , или ноль, чтобы вернуть все действия.</span><span class="sxs-lookup"><span data-stu-id="87465-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="87465-110">заполняет Массив, используемый для хранения маркеров разрешений.</span><span class="sxs-lookup"><span data-stu-id="87465-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="87465-111">[in] Максимальный размер массива `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="87465-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="87465-112">заполняет Число маркеров разрешений, возвращаемых в `rPermission` .</span><span class="sxs-lookup"><span data-stu-id="87465-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87465-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="87465-113">Return Value</span></span>  
  
|<span data-ttu-id="87465-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87465-114">HRESULT</span></span>|<span data-ttu-id="87465-115">Описание</span><span class="sxs-lookup"><span data-stu-id="87465-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="87465-116">`EnumPermissionSets` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="87465-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="87465-117">Нет токенов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="87465-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="87465-118">В этом случае значение `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="87465-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87465-119">Требования</span><span class="sxs-lookup"><span data-stu-id="87465-119">Requirements</span></span>  

 <span data-ttu-id="87465-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87465-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87465-121">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="87465-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="87465-122">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="87465-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="87465-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87465-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87465-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="87465-124">See also</span></span>

- [<span data-ttu-id="87465-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="87465-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="87465-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="87465-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
