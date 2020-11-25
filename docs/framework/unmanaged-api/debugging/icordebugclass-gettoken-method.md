---
title: Метод ICorDebugClass::GetToken
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetToken
helpviewer_keywords:
- GetToken method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetToken method [.NET Framework debugging]
ms.assetid: ee5c848a-eac4-4462-b07a-07ccd76a75df
topic_type:
- apiref
ms.openlocfilehash: 59f450117d1a52ce7b900d9d67330fc98281afa0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728424"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="63584-102">Метод ICorDebugClass::GetToken</span><span class="sxs-lookup"><span data-stu-id="63584-102">ICorDebugClass::GetToken Method</span></span>

<span data-ttu-id="63584-103">Возвращает `TypeDef` токен метаданных, который ссылается на определение этого класса.</span><span class="sxs-lookup"><span data-stu-id="63584-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63584-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63584-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63584-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="63584-105">Parameters</span></span>  

 `pTypeDef`  
 <span data-ttu-id="63584-106">заполняет Указатель на `mdTypeDef` маркер, который ссылается на определение этого класса.</span><span class="sxs-lookup"><span data-stu-id="63584-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63584-107">Требования</span><span class="sxs-lookup"><span data-stu-id="63584-107">Requirements</span></span>  

 <span data-ttu-id="63584-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63584-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63584-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63584-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63584-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63584-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63584-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63584-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63584-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="63584-112">See also</span></span>

- [<span data-ttu-id="63584-113">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="63584-113">Metadata Interfaces</span></span>](../metadata/metadata-interfaces.md)
