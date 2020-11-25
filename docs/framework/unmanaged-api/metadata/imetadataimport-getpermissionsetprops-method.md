---
title: Метод IMetaDataImport::GetPermissionSetProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
ms.openlocfilehash: 89c45c049ebadf9e1f16bef8d2626b4e2a17fb70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729256"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="54b85-102">Метод IMetaDataImport::GetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="54b85-102">IMetaDataImport::GetPermissionSetProps Method</span></span>

<span data-ttu-id="54b85-103">Возвращает метаданные, связанные с <xref:System.Security.PermissionSet?displayProperty=nameWithType> объектом, представленным указанным маркером разрешений.</span><span class="sxs-lookup"><span data-stu-id="54b85-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54b85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54b85-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54b85-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="54b85-105">Parameters</span></span>  

 `pm`  
 <span data-ttu-id="54b85-106">окне Маркер метаданных разрешения, представляющий набор разрешений, для которого необходимо получить свойства метаданных.</span><span class="sxs-lookup"><span data-stu-id="54b85-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="54b85-107">заполняет Указатель на набор разрешений.</span><span class="sxs-lookup"><span data-stu-id="54b85-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="54b85-108">заполняет Указатель на сигнатуру двоичных метаданных набора разрешений.</span><span class="sxs-lookup"><span data-stu-id="54b85-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="54b85-109">заполняет Размер в байтах для `ppvPermission` .</span><span class="sxs-lookup"><span data-stu-id="54b85-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54b85-110">Требования</span><span class="sxs-lookup"><span data-stu-id="54b85-110">Requirements</span></span>  

 <span data-ttu-id="54b85-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54b85-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54b85-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="54b85-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="54b85-113">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="54b85-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="54b85-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54b85-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54b85-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="54b85-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="54b85-116">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="54b85-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="54b85-117">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="54b85-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
