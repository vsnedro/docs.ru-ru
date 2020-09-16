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
ms.openlocfilehash: 8e119093800ea0a0119ba25ba38cf2eaf9afe96b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540866"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="92c9c-102">Метод IMetaDataDispenserEx::OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="92c9c-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="92c9c-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="92c9c-103">This method is not implemented.</span></span> <span data-ttu-id="92c9c-104">При вызове возвращается E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="92c9c-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92c9c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92c9c-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92c9c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="92c9c-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="92c9c-107">окне Указатель на интерфейс [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) , предоставляющий сведения о типе, в котором следует открыть область.</span><span class="sxs-lookup"><span data-stu-id="92c9c-107">[in] Pointer to an [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="92c9c-108">окне Флаги режима открытия.</span><span class="sxs-lookup"><span data-stu-id="92c9c-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="92c9c-109">окне Требуемый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="92c9c-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="92c9c-110">заполняет Указатель на указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="92c9c-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92c9c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="92c9c-111">Requirements</span></span>  
 <span data-ttu-id="92c9c-112">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92c9c-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92c9c-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="92c9c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92c9c-114">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="92c9c-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="92c9c-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92c9c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92c9c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="92c9c-116">See also</span></span>

- [<span data-ttu-id="92c9c-117">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="92c9c-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="92c9c-118">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="92c9c-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
