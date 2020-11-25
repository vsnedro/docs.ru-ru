---
title: Метод ICLRDataTarget::GetImageBase
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
ms.openlocfilehash: f1b9f55a383f1deb867c6b3e2fa385a82158d1e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703581"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="86f6e-102">Метод ICLRDataTarget::GetImageBase</span><span class="sxs-lookup"><span data-stu-id="86f6e-102">ICLRDataTarget::GetImageBase Method</span></span>

<span data-ttu-id="86f6e-103">Возвращает адрес базовой памяти указанного образа.</span><span class="sxs-lookup"><span data-stu-id="86f6e-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86f6e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86f6e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86f6e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="86f6e-105">Parameters</span></span>  

 `imagePath`  
 <span data-ttu-id="86f6e-106">окне Имя файла образа, включая его путь.</span><span class="sxs-lookup"><span data-stu-id="86f6e-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="86f6e-107">заполняет Указатель на CLRDATA_ADDRESS, в котором хранится базовый адрес изображения.</span><span class="sxs-lookup"><span data-stu-id="86f6e-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86f6e-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="86f6e-108">Remarks</span></span>  

 <span data-ttu-id="86f6e-109">Имя файла изображения может содержать или не иметь пути.</span><span class="sxs-lookup"><span data-stu-id="86f6e-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="86f6e-110">Если указан путь, сопоставление выполняется по всему пути; в противном случае сопоставление выполняется только с именем файла.</span><span class="sxs-lookup"><span data-stu-id="86f6e-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86f6e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="86f6e-111">Requirements</span></span>  

 <span data-ttu-id="86f6e-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86f6e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86f6e-113">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="86f6e-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="86f6e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86f6e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86f6e-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86f6e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86f6e-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="86f6e-116">See also</span></span>

- [<span data-ttu-id="86f6e-117">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="86f6e-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
