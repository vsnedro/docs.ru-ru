---
title: Метод IMetaDataDispenserEx::GetCORSystemDirectory
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetCORSystemDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type:
- apiref
ms.openlocfilehash: ea0e6f96028afc201f498119976eb87aa762a6eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681695"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="3178b-102">Метод IMetaDataDispenserEx::GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="3178b-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>

<span data-ttu-id="3178b-103">Возвращает каталог, содержащий текущую среду CLR.</span><span class="sxs-lookup"><span data-stu-id="3178b-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="3178b-104">Этот метод поддерживается только для использования необработанными отладчиками.</span><span class="sxs-lookup"><span data-stu-id="3178b-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="3178b-105">Если вызывается из другого компонента, он возвратит E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="3178b-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3178b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3178b-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3178b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="3178b-107">Parameters</span></span>  

 `szBuffer`  
 <span data-ttu-id="3178b-108">заполняет Буфер для получения имени каталога.</span><span class="sxs-lookup"><span data-stu-id="3178b-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="3178b-109">окне Размер (в байтах) `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="3178b-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="3178b-110">заполняет Число байтов, фактически возвращаемых в `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="3178b-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3178b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3178b-111">Requirements</span></span>  

 <span data-ttu-id="3178b-112">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3178b-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3178b-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="3178b-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3178b-114">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3178b-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3178b-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3178b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3178b-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3178b-116">See also</span></span>

- [<span data-ttu-id="3178b-117">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="3178b-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="3178b-118">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="3178b-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
