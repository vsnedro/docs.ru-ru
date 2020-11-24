---
title: Метод ICorPublishProcess::IsManaged
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: dfe247bda75c3695c7c09b85729b4e057c13c62d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692635"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="94cd2-102">Метод ICorPublishProcess::IsManaged</span><span class="sxs-lookup"><span data-stu-id="94cd2-102">ICorPublishProcess::IsManaged Method</span></span>

<span data-ttu-id="94cd2-103">Возвращает значение, указывающее, известно ли для процесса, на который ссылается этот [ICorPublishProcess](icorpublishprocess-interface.md) , управляемый код.</span><span class="sxs-lookup"><span data-stu-id="94cd2-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94cd2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94cd2-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94cd2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="94cd2-105">Parameters</span></span>  

 `pbManaged`  
 <span data-ttu-id="94cd2-106">заполняет Указатель на логическое значение, указывающее, имеет ли процесс управляемый код.</span><span class="sxs-lookup"><span data-stu-id="94cd2-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="94cd2-107">Значение равно `true` , если процесс имеет управляемый код; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="94cd2-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94cd2-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="94cd2-108">Remarks</span></span>  

 <span data-ttu-id="94cd2-109">Поскольку текущая версия `ICorPublishProcess` разрешает доступ только к процессам, имеющим управляемый код, `IsManaged` всегда возвращает `true` .</span><span class="sxs-lookup"><span data-stu-id="94cd2-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94cd2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="94cd2-110">Requirements</span></span>  

 <span data-ttu-id="94cd2-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94cd2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94cd2-112">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="94cd2-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="94cd2-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94cd2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94cd2-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94cd2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94cd2-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="94cd2-115">See also</span></span>

- [<span data-ttu-id="94cd2-116">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="94cd2-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
