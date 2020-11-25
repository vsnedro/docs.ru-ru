---
title: Метод ICorDebugAssembly::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetName
helpviewer_keywords:
- ICorDebugAssembly::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: cdeda721-b214-4503-a291-c70b68b5f36b
topic_type:
- apiref
ms.openlocfilehash: 3794a3b308bd5c96a38337d8b81e61167e4dc988
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734053"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="cf9d1-102">Метод ICorDebugAssembly::GetName</span><span class="sxs-lookup"><span data-stu-id="cf9d1-102">ICorDebugAssembly::GetName Method</span></span>

<span data-ttu-id="cf9d1-103">Возвращает имя сборки, которую `ICorDebugAssembly` представляет этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="cf9d1-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf9d1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf9d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf9d1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cf9d1-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="cf9d1-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="cf9d1-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="cf9d1-107">заполняет Указатель на целое число, задающее фактическую длину имени.</span><span class="sxs-lookup"><span data-stu-id="cf9d1-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="cf9d1-108">заполняет Массив, в котором хранится имя.</span><span class="sxs-lookup"><span data-stu-id="cf9d1-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf9d1-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="cf9d1-109">Remarks</span></span>  

 <span data-ttu-id="cf9d1-110">`GetName`Метод возвращает полный путь и имя файла сборки.</span><span class="sxs-lookup"><span data-stu-id="cf9d1-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf9d1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="cf9d1-111">Requirements</span></span>  

 <span data-ttu-id="cf9d1-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf9d1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf9d1-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf9d1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf9d1-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf9d1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf9d1-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf9d1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
