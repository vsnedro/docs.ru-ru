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
ms.openlocfilehash: b29de0b70daa783197e78fe985d379d4124bc140
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205150"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="60a60-102">Метод ICorDebugFrame::GetCaller</span><span class="sxs-lookup"><span data-stu-id="60a60-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="60a60-103">Возвращает указатель на объект ICorDebugFrame в текущей цепочке, вызвавшей этот кадр.</span><span class="sxs-lookup"><span data-stu-id="60a60-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60a60-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60a60-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60a60-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="60a60-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="60a60-106">заполняет Указатель на адрес `ICorDebugFrame` объекта, представляющий вызывающий кадр.</span><span class="sxs-lookup"><span data-stu-id="60a60-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="60a60-107">Это значение равно null, если вызываемый кадр является самым внешним кадром в текущей цепочке.</span><span class="sxs-lookup"><span data-stu-id="60a60-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60a60-108">Требования</span><span class="sxs-lookup"><span data-stu-id="60a60-108">Requirements</span></span>  
 <span data-ttu-id="60a60-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60a60-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60a60-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60a60-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60a60-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60a60-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60a60-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60a60-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
