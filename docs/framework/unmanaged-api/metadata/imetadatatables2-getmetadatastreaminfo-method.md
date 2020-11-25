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
ms.openlocfilehash: 21fc79f62dba4b16a7a067dff8fb9dcc795c9d35
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708729"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="d42d2-102">Метод IMetaDataTables2::GetMetaDataStreamInfo</span><span class="sxs-lookup"><span data-stu-id="d42d2-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>

<span data-ttu-id="d42d2-103">Возвращает имя, размер и содержимое потока метаданных по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="d42d2-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d42d2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d42d2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d42d2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d42d2-105">Parameters</span></span>  

 `ix`  
 <span data-ttu-id="d42d2-106">окне Индекс запрошенного потока метаданных.</span><span class="sxs-lookup"><span data-stu-id="d42d2-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="d42d2-107">заполняет Указатель на имя потока.</span><span class="sxs-lookup"><span data-stu-id="d42d2-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="d42d2-108">заполняет Указатель на поток метаданных.</span><span class="sxs-lookup"><span data-stu-id="d42d2-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="d42d2-109">заполняет Размер (в байтах) `ppv` .</span><span class="sxs-lookup"><span data-stu-id="d42d2-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d42d2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d42d2-110">Requirements</span></span>  

 <span data-ttu-id="d42d2-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d42d2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d42d2-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="d42d2-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d42d2-113">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d42d2-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d42d2-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d42d2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d42d2-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d42d2-115">See also</span></span>

- [<span data-ttu-id="d42d2-116">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="d42d2-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
- [<span data-ttu-id="d42d2-117">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="d42d2-117">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
