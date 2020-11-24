---
title: Метод ICorDebugFrame::GetCaller
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
ms.openlocfilehash: b52499e509bf172b03b5e4d2b1e4c677dc800281
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690477"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="5aedc-102">Метод ICorDebugFrame::GetCaller</span><span class="sxs-lookup"><span data-stu-id="5aedc-102">ICorDebugFrame::GetCaller Method</span></span>

<span data-ttu-id="5aedc-103">Возвращает указатель на объект ICorDebugFrame в текущей цепочке, вызвавшей этот кадр.</span><span class="sxs-lookup"><span data-stu-id="5aedc-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aedc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5aedc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5aedc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5aedc-105">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="5aedc-106">заполняет Указатель на адрес `ICorDebugFrame` объекта, представляющий вызывающий кадр.</span><span class="sxs-lookup"><span data-stu-id="5aedc-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="5aedc-107">Это значение равно null, если вызываемый кадр является самым внешним кадром в текущей цепочке.</span><span class="sxs-lookup"><span data-stu-id="5aedc-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5aedc-108">Требования</span><span class="sxs-lookup"><span data-stu-id="5aedc-108">Requirements</span></span>  

 <span data-ttu-id="5aedc-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5aedc-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5aedc-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5aedc-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5aedc-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5aedc-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5aedc-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5aedc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
