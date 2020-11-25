---
title: Метод ICLRMetadataLocator::GetMetadata
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
ms.openlocfilehash: f0ba2342e9704ba06dd1d3612f699298c734a5eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723523"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="aa871-102">Метод ICLRMetadataLocator::GetMetadata</span><span class="sxs-lookup"><span data-stu-id="aa871-102">ICLRMetadataLocator::GetMetadata Method</span></span>

<span data-ttu-id="aa871-103">Вызывается службами доступа к данным среды CLR для получения метаданных изображения.</span><span class="sxs-lookup"><span data-stu-id="aa871-103">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa871-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa871-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa871-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aa871-105">Parameters</span></span>  

 `imagePath`  
 <span data-ttu-id="aa871-106">окне Строка, указывающая путь к файлу изображения.</span><span class="sxs-lookup"><span data-stu-id="aa871-106">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="aa871-107">окне Метка времени файла изображения.</span><span class="sxs-lookup"><span data-stu-id="aa871-107">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="aa871-108">окне Размер файла изображения.</span><span class="sxs-lookup"><span data-stu-id="aa871-108">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="aa871-109">окне Глобальный уникальный идентификатор изображения.</span><span class="sxs-lookup"><span data-stu-id="aa871-109">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="aa871-110">окне Относительный виртуальный адрес (RVA) метаданных.</span><span class="sxs-lookup"><span data-stu-id="aa871-110">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="aa871-111">Адрес отсчитывается относительно базового адреса образа.</span><span class="sxs-lookup"><span data-stu-id="aa871-111">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="aa871-112">[in] Зарезервирован для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="aa871-112">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="aa871-113">окне Размер буфера, в который следует поместить метаданные.</span><span class="sxs-lookup"><span data-stu-id="aa871-113">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="aa871-114">заполняет Буфер для размещения метаданных.</span><span class="sxs-lookup"><span data-stu-id="aa871-114">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="aa871-115">заполняет Размер возвращаемых метаданных.</span><span class="sxs-lookup"><span data-stu-id="aa871-115">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa871-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="aa871-116">Remarks</span></span>  

 <span data-ttu-id="aa871-117">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="aa871-117">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa871-118">Требования</span><span class="sxs-lookup"><span data-stu-id="aa871-118">Requirements</span></span>  

 <span data-ttu-id="aa871-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa871-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa871-120">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="aa871-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="aa871-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa871-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa871-122">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa871-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa871-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aa871-123">See also</span></span>

- [<span data-ttu-id="aa871-124">Интерфейс ICLRMetadataLocator</span><span class="sxs-lookup"><span data-stu-id="aa871-124">ICLRMetadataLocator Interface</span></span>](iclrmetadatalocator-interface.md)
