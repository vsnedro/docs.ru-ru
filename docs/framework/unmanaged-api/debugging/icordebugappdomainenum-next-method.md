---
title: Метод ICorDebugAppDomainEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type:
- apiref
ms.openlocfilehash: b315f38dc306727e33b52b84d17951a91ccdc39f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684477"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="1d472-102">Метод ICorDebugAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="1d472-102">ICorDebugAppDomainEnum::Next Method</span></span>

<span data-ttu-id="1d472-103">Возвращает указанное число доменов приложений из коллекции, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="1d472-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d472-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d472-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d472-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d472-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="1d472-106">окне Число извлекаемых доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="1d472-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="1d472-107">заполняет Массив указателей, каждый из которых указывает на объект ICorDebugAppDomain, представляющий домен приложения.</span><span class="sxs-lookup"><span data-stu-id="1d472-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="1d472-108">заполняет Указатель на число фактически возвращенных доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="1d472-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="1d472-109">Это значение может быть равно NULL `celt` , если равно единице.</span><span class="sxs-lookup"><span data-stu-id="1d472-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d472-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1d472-110">Requirements</span></span>  

 <span data-ttu-id="1d472-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d472-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d472-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d472-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d472-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d472-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d472-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d472-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
