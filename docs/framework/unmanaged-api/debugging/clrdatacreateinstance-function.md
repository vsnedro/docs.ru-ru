---
title: Функция CLRDataCreateInstance
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
ms.openlocfilehash: 2ffc575cfcef1089a70ef3b6d38787a5b4c50443
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729828"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="384ab-102">Функция CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="384ab-102">CLRDataCreateInstance Function</span></span>

<span data-ttu-id="384ab-103">Создает объект интерфейса для указанного целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="384ab-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="384ab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="384ab-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,
    [in]  ICLRDataTarget  *target,
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="384ab-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="384ab-105">Parameters</span></span>  

 `iid`  
 <span data-ttu-id="384ab-106">окне Идентификатор интерфейса, для которого создается экземпляр.</span><span class="sxs-lookup"><span data-stu-id="384ab-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="384ab-107">окне Указатель на реализуемый пользователем объект [ICLRDataTarget](iclrdatatarget-interface.md) , представляющий целевой элемент, для которого создается объект интерфейса.</span><span class="sxs-lookup"><span data-stu-id="384ab-107">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="384ab-108">заполняет Указатель на адрес возвращенного объекта интерфейса.</span><span class="sxs-lookup"><span data-stu-id="384ab-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="384ab-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="384ab-109">Remarks</span></span>  

 <span data-ttu-id="384ab-110">`ICLRDataTarget`Объект реализуется модулем записи приложения отладки.</span><span class="sxs-lookup"><span data-stu-id="384ab-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="384ab-111">Реализация зависит от типа представляемого целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="384ab-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="384ab-112">Целевой элемент может быть процессом, дампом памяти, удаленным компьютером и т. д.</span><span class="sxs-lookup"><span data-stu-id="384ab-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="384ab-113">Требования</span><span class="sxs-lookup"><span data-stu-id="384ab-113">Requirements</span></span>  

 <span data-ttu-id="384ab-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="384ab-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="384ab-115">**Заголовок:** Клрдата. idl</span><span class="sxs-lookup"><span data-stu-id="384ab-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="384ab-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="384ab-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="384ab-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="384ab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="384ab-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="384ab-118">See also</span></span>

- [<span data-ttu-id="384ab-119">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="384ab-119">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
