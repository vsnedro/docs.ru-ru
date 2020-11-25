---
title: Метод ICeeGen::AllocateMethodBuffer
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
ms.openlocfilehash: e1849eb95401e3637a1fd1b00715332f9886071e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715528"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="ddeea-102">Метод ICeeGen::AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="ddeea-102">ICeeGen::AllocateMethodBuffer Method</span></span>

<span data-ttu-id="ddeea-103">Создает буфер указанного размера для метода и получает относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="ddeea-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="ddeea-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="ddeea-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddeea-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ddeea-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (
    [in]  ULONG    cchBuffer,
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddeea-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ddeea-106">Parameters</span></span>  

 `cchBuffer`  
 <span data-ttu-id="ddeea-107">окне Длина создаваемого буфера.</span><span class="sxs-lookup"><span data-stu-id="ddeea-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="ddeea-108">заполняет Возвращаемый буфер.</span><span class="sxs-lookup"><span data-stu-id="ddeea-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="ddeea-109">заполняет Относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="ddeea-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddeea-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ddeea-110">Requirements</span></span>  

 <span data-ttu-id="ddeea-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddeea-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddeea-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="ddeea-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ddeea-113">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ddeea-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ddeea-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddeea-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddeea-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ddeea-115">See also</span></span>

- [<span data-ttu-id="ddeea-116">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="ddeea-116">ICeeGen Interface</span></span>](iceegen-interface.md)
