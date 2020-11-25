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
ms.openlocfilehash: 077aa50465d99c9098f26e67b3852feb0d399142
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703529"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="f2e13-102">Метод ICLRDataTarget::GetPointerSize</span><span class="sxs-lookup"><span data-stu-id="f2e13-102">ICLRDataTarget::GetPointerSize Method</span></span>

<span data-ttu-id="f2e13-103">Возвращает размер (в байтах) типа указателя, используемого целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="f2e13-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="f2e13-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f2e13-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2e13-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2e13-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2e13-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f2e13-106">Parameters</span></span>  

 `pointerSize`  
 <span data-ttu-id="f2e13-107">заполняет Указатель на целочисленное значение, указывающее размер (в байтах) указателя на целевой процесс.</span><span class="sxs-lookup"><span data-stu-id="f2e13-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2e13-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f2e13-108">Remarks</span></span>  

 <span data-ttu-id="f2e13-109">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="f2e13-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2e13-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f2e13-110">Requirements</span></span>  

 <span data-ttu-id="f2e13-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2e13-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2e13-112">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="f2e13-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f2e13-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2e13-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2e13-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2e13-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2e13-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f2e13-115">See also</span></span>

- [<span data-ttu-id="f2e13-116">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="f2e13-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
