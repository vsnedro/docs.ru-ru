---
title: Метод ISymUnmanagedReader::GetMethodVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
ms.openlocfilehash: b0590f93c6a4c5ef28e03fc909c1f6a1474e5fad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720611"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="03a4a-102">Метод ISymUnmanagedReader::GetMethodVersion</span><span class="sxs-lookup"><span data-stu-id="03a4a-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>

<span data-ttu-id="03a4a-103">Возвращает версию метода.</span><span class="sxs-lookup"><span data-stu-id="03a4a-103">Gets the method version.</span></span> <span data-ttu-id="03a4a-104">Версия метода начинается с 1 и увеличивается каждый раз при повторной компиляции метода.</span><span class="sxs-lookup"><span data-stu-id="03a4a-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="03a4a-105">Перекомпиляция может произойти без изменения метода.</span><span class="sxs-lookup"><span data-stu-id="03a4a-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03a4a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03a4a-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03a4a-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="03a4a-107">Parameters</span></span>  

 `pMethod`  
 <span data-ttu-id="03a4a-108">окне Метод, для которого необходимо получить версию.</span><span class="sxs-lookup"><span data-stu-id="03a4a-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="03a4a-109">заполняет Указатель на переменную, которая получает версию метода.</span><span class="sxs-lookup"><span data-stu-id="03a4a-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03a4a-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="03a4a-110">Return Value</span></span>  

 <span data-ttu-id="03a4a-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="03a4a-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03a4a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="03a4a-112">Requirements</span></span>  

 <span data-ttu-id="03a4a-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="03a4a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03a4a-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="03a4a-114">See also</span></span>

- [<span data-ttu-id="03a4a-115">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="03a4a-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
