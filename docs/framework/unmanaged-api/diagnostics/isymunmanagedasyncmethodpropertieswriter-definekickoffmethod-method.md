---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: 418a77855d1cb34a07f5957059b5a6f5a106c321
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707091"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="7e8e7-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="7e8e7-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>

<span data-ttu-id="7e8e7-103">Задает начальный метод, инициирующий асинхронную операцию.</span><span class="sxs-lookup"><span data-stu-id="7e8e7-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e8e7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e8e7-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e8e7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e8e7-105">Parameters</span></span>  
  
|<span data-ttu-id="7e8e7-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="7e8e7-106">Parameter</span></span>|<span data-ttu-id="7e8e7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7e8e7-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="7e8e7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7e8e7-108">Return Value</span></span>  

 <span data-ttu-id="7e8e7-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="7e8e7-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e8e7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7e8e7-110">Requirements</span></span>  

 <span data-ttu-id="7e8e7-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="7e8e7-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e8e7-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7e8e7-112">See also</span></span>

- [<span data-ttu-id="7e8e7-113">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="7e8e7-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
