---
title: Метод ICorDebug::Initialize
ms.date: 03/30/2017
api_name:
- ICorDebug.Initialize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type:
- apiref
ms.openlocfilehash: aeecf19cb85ce5d7781c3dfedca079e97cab76ce
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895360"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="fba56-102">Метод ICorDebug::Initialize</span><span class="sxs-lookup"><span data-stu-id="fba56-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="fba56-103">Инициализирует объект `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="fba56-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fba56-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fba56-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="fba56-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="fba56-105">Remarks</span></span>  
 <span data-ttu-id="fba56-106">Отладчик должен вызвать `Initialize` во время создания, чтобы инициализировать службы отладки.</span><span class="sxs-lookup"><span data-stu-id="fba56-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="fba56-107">Этот метод должен вызываться до вызова любого другого метода `ICorDebug` .</span><span class="sxs-lookup"><span data-stu-id="fba56-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fba56-108">Требования</span><span class="sxs-lookup"><span data-stu-id="fba56-108">Requirements</span></span>  
 <span data-ttu-id="fba56-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fba56-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fba56-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fba56-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fba56-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fba56-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fba56-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fba56-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fba56-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fba56-113">See also</span></span>

- [<span data-ttu-id="fba56-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="fba56-114">ICorDebug Interface</span></span>](icordebug-interface.md)
