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
ms.openlocfilehash: 71b07e11cd3fec1a0dbebe986d98067c2e6f18e1
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860629"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="553f2-102">Метод ICLRDataTarget::GetImageBase</span><span class="sxs-lookup"><span data-stu-id="553f2-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="553f2-103">Возвращает адрес базовой памяти указанного образа.</span><span class="sxs-lookup"><span data-stu-id="553f2-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="553f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="553f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="553f2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="553f2-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="553f2-106">окне Имя файла образа, включая его путь.</span><span class="sxs-lookup"><span data-stu-id="553f2-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="553f2-107">заполняет Указатель на CLRDATA_ADDRESS, в котором хранится базовый адрес изображения.</span><span class="sxs-lookup"><span data-stu-id="553f2-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="553f2-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="553f2-108">Remarks</span></span>  
 <span data-ttu-id="553f2-109">Имя файла изображения может содержать или не иметь пути.</span><span class="sxs-lookup"><span data-stu-id="553f2-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="553f2-110">Если указан путь, сопоставление выполняется по всему пути; в противном случае сопоставление выполняется только с именем файла.</span><span class="sxs-lookup"><span data-stu-id="553f2-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="553f2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="553f2-111">Requirements</span></span>  
 <span data-ttu-id="553f2-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="553f2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="553f2-113">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="553f2-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="553f2-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="553f2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="553f2-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="553f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="553f2-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="553f2-116">See also</span></span>

- [<span data-ttu-id="553f2-117">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="553f2-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
