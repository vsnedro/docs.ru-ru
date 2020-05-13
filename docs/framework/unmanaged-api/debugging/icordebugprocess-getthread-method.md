---
title: Метод ICorDebugProcess::GetThread
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThread
helpviewer_keywords:
- ICorDebugProcess::GetThread method [.NET Framework debugging]
- GetThread method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a48261ed-700b-41c9-8cb4-18c526546603
topic_type:
- apiref
ms.openlocfilehash: 081852f91f243c4a979e2969220e71bd10c8c56b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212894"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="e9b86-102">Метод ICorDebugProcess::GetThread</span><span class="sxs-lookup"><span data-stu-id="e9b86-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="e9b86-103">Возвращает поток этого процесса с указанным ИДЕНТИФИКАТОРом потока операционной системы (ОС).</span><span class="sxs-lookup"><span data-stu-id="e9b86-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b86-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9b86-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9b86-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9b86-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="e9b86-106">окне Идентификатор потока операционной системы для извлекаемого потока.</span><span class="sxs-lookup"><span data-stu-id="e9b86-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="e9b86-107">заполняет Указатель на адрес объекта ICorDebugThread, представляющего поток.</span><span class="sxs-lookup"><span data-stu-id="e9b86-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9b86-108">Требования</span><span class="sxs-lookup"><span data-stu-id="e9b86-108">Requirements</span></span>  
 <span data-ttu-id="e9b86-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9b86-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9b86-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9b86-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9b86-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9b86-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9b86-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9b86-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
