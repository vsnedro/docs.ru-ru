---
title: Метод ICLRDataTarget::GetMachineType
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetMachineType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetMachineType
helpviewer_keywords:
- ICLRDataTarget::GetMachineType method [.NET Framework debugging]
- GetMachineType method [.NET Framework debugging]
ms.assetid: 5f1f9c61-3e3b-48b2-b111-a4395f7623a7
topic_type:
- apiref
ms.openlocfilehash: 9d86b23b91702929a86334f557a8d647e19861a4
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860590"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="759cf-102">Метод ICLRDataTarget::GetMachineType</span><span class="sxs-lookup"><span data-stu-id="759cf-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="759cf-103">Возвращает идентификатор для типа набора инструкций, используемого целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="759cf-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="759cf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="759cf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="759cf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="759cf-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="759cf-106">заполняет Указатель на значение, указывающее набор инструкций, который используется целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="759cf-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="759cf-107">Возвращаемое `machineType` значение является одной из IMAGE_FILE_MACHINE констант, которые определены в файле заголовка WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="759cf-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="759cf-108">Требования</span><span class="sxs-lookup"><span data-stu-id="759cf-108">Requirements</span></span>  
 <span data-ttu-id="759cf-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="759cf-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="759cf-110">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="759cf-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="759cf-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="759cf-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="759cf-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="759cf-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="759cf-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="759cf-113">See also</span></span>

- [<span data-ttu-id="759cf-114">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="759cf-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
