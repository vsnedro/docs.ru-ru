---
title: Метод IMapToken::Map
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
ms.openlocfilehash: 51cca1ab61027090b0d22781dfd740038bc9372d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718206"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="bc4bd-102">Метод IMapToken::Map</span><span class="sxs-lookup"><span data-stu-id="bc4bd-102">IMapToken::Map Method</span></span>

<span data-ttu-id="bc4bd-103">Сопоставляет связь между сборками, используя подписи метаданных.</span><span class="sxs-lookup"><span data-stu-id="bc4bd-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc4bd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc4bd-104">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc4bd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bc4bd-105">Parameters</span></span>  

 `tkImp`  
 <span data-ttu-id="bc4bd-106">окне Токен метаданных, представляющий импортированный объект кода.</span><span class="sxs-lookup"><span data-stu-id="bc4bd-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="bc4bd-107">окне Токен метаданных, представляющий созданный объект кода.</span><span class="sxs-lookup"><span data-stu-id="bc4bd-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc4bd-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="bc4bd-108">Remarks</span></span>  

 <span data-ttu-id="bc4bd-109">Когда повторное отображение токена происходит во время слияния, исходный маркер ограничивается в импортированной (исходной) области метаданных, а новый маркер — в области исрожденных (целевых) метаданных.</span><span class="sxs-lookup"><span data-stu-id="bc4bd-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc4bd-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bc4bd-110">Requirements</span></span>  

 <span data-ttu-id="bc4bd-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc4bd-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc4bd-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="bc4bd-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc4bd-113">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bc4bd-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc4bd-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc4bd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc4bd-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bc4bd-115">See also</span></span>

- [<span data-ttu-id="bc4bd-116">Интерфейс IMapToken</span><span class="sxs-lookup"><span data-stu-id="bc4bd-116">IMapToken Interface</span></span>](imaptoken-interface.md)
