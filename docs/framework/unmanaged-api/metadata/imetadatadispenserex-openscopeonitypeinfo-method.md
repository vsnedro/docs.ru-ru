---
title: Метод IMetaDataDispenserEx::OpenScopeOnITypeInfo
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type:
- apiref
ms.openlocfilehash: 91ef9eaa855ed841bc75bfaeead462f045eb1d8b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007459"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="d780f-102">Метод IMetaDataDispenserEx::OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="d780f-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="d780f-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="d780f-103">This method is not implemented.</span></span> <span data-ttu-id="d780f-104">При вызове возвращается E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="d780f-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d780f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d780f-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d780f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d780f-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="d780f-107">окне Указатель на интерфейс [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) , предоставляющий сведения о типе, в котором следует открыть область.</span><span class="sxs-lookup"><span data-stu-id="d780f-107">[in] Pointer to an [ITypeInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="d780f-108">окне Флаги режима открытия.</span><span class="sxs-lookup"><span data-stu-id="d780f-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="d780f-109">окне Требуемый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d780f-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="d780f-110">заполняет Указатель на указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d780f-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d780f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d780f-111">Requirements</span></span>  
 <span data-ttu-id="d780f-112">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d780f-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d780f-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="d780f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d780f-114">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d780f-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d780f-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d780f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d780f-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d780f-116">See also</span></span>

- [<span data-ttu-id="d780f-117">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="d780f-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="d780f-118">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="d780f-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
