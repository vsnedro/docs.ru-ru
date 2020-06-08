---
title: Метод IMetaDataTables2::GetMetaDataStreamInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
ms.openlocfilehash: 7d39d089c348b7320651ed21ea14ba07d7877fd4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501112"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="e77e9-102">Метод IMetaDataTables2::GetMetaDataStreamInfo</span><span class="sxs-lookup"><span data-stu-id="e77e9-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="e77e9-103">Возвращает имя, размер и содержимое потока метаданных по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="e77e9-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e77e9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e77e9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e77e9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e77e9-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="e77e9-106">окне Индекс запрошенного потока метаданных.</span><span class="sxs-lookup"><span data-stu-id="e77e9-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="e77e9-107">заполняет Указатель на имя потока.</span><span class="sxs-lookup"><span data-stu-id="e77e9-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="e77e9-108">заполняет Указатель на поток метаданных.</span><span class="sxs-lookup"><span data-stu-id="e77e9-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="e77e9-109">заполняет Размер (в байтах) `ppv` .</span><span class="sxs-lookup"><span data-stu-id="e77e9-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e77e9-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e77e9-110">Requirements</span></span>  
 <span data-ttu-id="e77e9-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e77e9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e77e9-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="e77e9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e77e9-113">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e77e9-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e77e9-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e77e9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e77e9-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e77e9-115">See also</span></span>

- [<span data-ttu-id="e77e9-116">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="e77e9-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
- [<span data-ttu-id="e77e9-117">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="e77e9-117">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
