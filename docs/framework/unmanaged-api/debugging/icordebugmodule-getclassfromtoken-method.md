---
title: Метод ICorDebugModule::GetClassFromToken
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetClassFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetClassFromToken
helpviewer_keywords:
- GetClassFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetClassFromToken method [.NET Framework debugging]
ms.assetid: 622a4d3c-0425-4c54-a7e4-0735377cdad2
topic_type:
- apiref
ms.openlocfilehash: f8a56dcf03748c6582bce07fc379113c5cdddd11
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212618"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="fc982-102">Метод ICorDebugModule::GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="fc982-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="fc982-103">Возвращает класс, указанный токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="fc982-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc982-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc982-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc982-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc982-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="fc982-106">окне `mdTypeDef`Токен метаданных, который ссылается на метаданные класса.</span><span class="sxs-lookup"><span data-stu-id="fc982-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="fc982-107">заполняет Указатель на адрес объекта ICorDebugClass, который представляет класс.</span><span class="sxs-lookup"><span data-stu-id="fc982-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc982-108">Требования</span><span class="sxs-lookup"><span data-stu-id="fc982-108">Requirements</span></span>  
 <span data-ttu-id="fc982-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc982-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc982-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc982-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc982-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc982-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc982-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc982-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
