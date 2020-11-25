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
ms.openlocfilehash: 00601e0bc722c0dc5e972324eddc0ab073d04586
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703542"
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="c2c7b-102">Метод ICLRDataTarget::GetMachineType</span><span class="sxs-lookup"><span data-stu-id="c2c7b-102">ICLRDataTarget::GetMachineType Method</span></span>

<span data-ttu-id="c2c7b-103">Возвращает идентификатор для типа набора инструкций, используемого целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="c2c7b-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2c7b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2c7b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2c7b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2c7b-105">Parameters</span></span>  

 `machineType`  
 <span data-ttu-id="c2c7b-106">заполняет Указатель на значение, указывающее набор инструкций, который используется целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="c2c7b-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="c2c7b-107">Возвращаемое значение `machineType` является одной из IMAGE_FILE_MACHINE констант, которые определены в файле заголовка WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="c2c7b-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2c7b-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c2c7b-108">Requirements</span></span>  

 <span data-ttu-id="c2c7b-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2c7b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2c7b-110">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="c2c7b-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c2c7b-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2c7b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2c7b-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2c7b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2c7b-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c2c7b-113">See also</span></span>

- [<span data-ttu-id="c2c7b-114">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="c2c7b-114">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
