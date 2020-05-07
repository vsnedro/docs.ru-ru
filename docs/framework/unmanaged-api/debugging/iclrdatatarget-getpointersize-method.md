---
title: Метод ICLRDataTarget::GetPointerSize
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetPointerSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetPointerSize
helpviewer_keywords:
- GetPointerSize method [.NET Framework debugging]
- ICLRDataTarget::GetPointerSize method [.NET Framework debugging]
ms.assetid: 51d9f4a4-81a7-4527-8537-5212bdb05c70
topic_type:
- apiref
ms.openlocfilehash: e6c4d5f8cc911198add176cab9c4b9b89128068e
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860622"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="d277a-102">Метод ICLRDataTarget::GetPointerSize</span><span class="sxs-lookup"><span data-stu-id="d277a-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="d277a-103">Возвращает размер (в байтах) типа указателя, используемого целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="d277a-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="d277a-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d277a-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d277a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d277a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d277a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d277a-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="d277a-107">заполняет Указатель на целочисленное значение, указывающее размер (в байтах) указателя на целевой процесс.</span><span class="sxs-lookup"><span data-stu-id="d277a-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d277a-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="d277a-108">Remarks</span></span>  
 <span data-ttu-id="d277a-109">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="d277a-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d277a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d277a-110">Requirements</span></span>  
 <span data-ttu-id="d277a-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d277a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d277a-112">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="d277a-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d277a-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d277a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d277a-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d277a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d277a-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d277a-115">See also</span></span>

- [<span data-ttu-id="d277a-116">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="d277a-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
