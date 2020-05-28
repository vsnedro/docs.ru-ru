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
ms.openlocfilehash: a76c17e663fdf6555ed878cca1b86b6a9395730e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008798"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="3533c-102">Метод IMetaDataDispenserEx::GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="3533c-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="3533c-103">Возвращает каталог, содержащий текущую среду CLR.</span><span class="sxs-lookup"><span data-stu-id="3533c-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="3533c-104">Этот метод поддерживается только для использования необработанными отладчиками.</span><span class="sxs-lookup"><span data-stu-id="3533c-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="3533c-105">Если вызывается из другого компонента, он возвратит E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="3533c-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3533c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3533c-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3533c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="3533c-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="3533c-108">заполняет Буфер для получения имени каталога.</span><span class="sxs-lookup"><span data-stu-id="3533c-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="3533c-109">окне Размер (в байтах) `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="3533c-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="3533c-110">заполняет Число байтов, фактически возвращаемых в `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="3533c-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3533c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3533c-111">Requirements</span></span>  
 <span data-ttu-id="3533c-112">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3533c-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3533c-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="3533c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3533c-114">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3533c-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3533c-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3533c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3533c-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="3533c-116">See also</span></span>

- [<span data-ttu-id="3533c-117">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="3533c-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="3533c-118">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="3533c-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
