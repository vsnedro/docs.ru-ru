---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: c35455fc679d79d56814a9c2f026ec395e944f24
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441725"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="78a4b-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="78a4b-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="78a4b-103">Задает начальный метод, инициирующий асинхронную операцию.</span><span class="sxs-lookup"><span data-stu-id="78a4b-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a4b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78a4b-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78a4b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="78a4b-105">Parameters</span></span>  
  
|<span data-ttu-id="78a4b-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="78a4b-106">Parameter</span></span>|<span data-ttu-id="78a4b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="78a4b-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="78a4b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="78a4b-108">Return Value</span></span>  
 <span data-ttu-id="78a4b-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="78a4b-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78a4b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="78a4b-110">Requirements</span></span>  
 <span data-ttu-id="78a4b-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="78a4b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a4b-112">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="78a4b-112">See also</span></span>

- [<span data-ttu-id="78a4b-113">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="78a4b-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
