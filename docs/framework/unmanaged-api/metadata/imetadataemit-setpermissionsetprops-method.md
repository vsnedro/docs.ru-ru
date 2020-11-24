---
title: Метод IMetaDataEmit::SetPermissionSetProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
ms.openlocfilehash: 4c3e0953d71020ba62ee4ab68aa9e21ea3f0f521
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675039"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="ab2ab-102">Метод IMetaDataEmit::SetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="ab2ab-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>

<span data-ttu-id="ab2ab-103">Задает или обновляет функции сигнатуры метаданных набора разрешений, определенного при предыдущем вызове метода [IMetaDataEmit::D ефинепермиссионсет](imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="ab2ab-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab2ab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab2ab-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab2ab-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ab2ab-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="ab2ab-106">окне Токен метаданных, представляющий объект для декорирования.</span><span class="sxs-lookup"><span data-stu-id="ab2ab-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="ab2ab-107">окне Значение [кордеклсекурити](cordeclsecurity-enumeration.md) , указывающее тип используемой декларативной безопасности.</span><span class="sxs-lookup"><span data-stu-id="ab2ab-107">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="ab2ab-108">окне Большой двоичный объект разрешений.</span><span class="sxs-lookup"><span data-stu-id="ab2ab-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="ab2ab-109">окне Размер (в байтах) `pvPermission` .</span><span class="sxs-lookup"><span data-stu-id="ab2ab-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="ab2ab-110">заполняет `mdPermission` Токен метаданных, представляющий обновленные разрешения.</span><span class="sxs-lookup"><span data-stu-id="ab2ab-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab2ab-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ab2ab-111">Requirements</span></span>  

 <span data-ttu-id="ab2ab-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab2ab-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab2ab-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="ab2ab-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab2ab-114">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ab2ab-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab2ab-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab2ab-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab2ab-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ab2ab-116">See also</span></span>

- [<span data-ttu-id="ab2ab-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="ab2ab-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ab2ab-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="ab2ab-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
