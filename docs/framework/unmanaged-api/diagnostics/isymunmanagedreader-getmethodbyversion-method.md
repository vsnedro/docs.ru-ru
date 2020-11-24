---
title: Метод ISymUnmanagedReader::GetMethodByVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
ms.openlocfilehash: 64e6b9a1942e9a69e43de3d2f09564814328ec08
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689619"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="6e15e-102">Метод ISymUnmanagedReader::GetMethodByVersion</span><span class="sxs-lookup"><span data-stu-id="6e15e-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>

<span data-ttu-id="6e15e-103">Возвращает метод чтения символов по заданному маркеру метода и номеру версии для редактирования и копирования.</span><span class="sxs-lookup"><span data-stu-id="6e15e-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="6e15e-104">Номера версий начинаются с 1 и увеличиваются каждый раз при изменении метода в результате операции редактирования и копирования.</span><span class="sxs-lookup"><span data-stu-id="6e15e-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e15e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e15e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e15e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e15e-106">Parameters</span></span>  

 `token`  
 <span data-ttu-id="6e15e-107">окне Токен метода.</span><span class="sxs-lookup"><span data-stu-id="6e15e-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="6e15e-108">окне Версия метода.</span><span class="sxs-lookup"><span data-stu-id="6e15e-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="6e15e-109">заполняет Указатель на возвращаемый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="6e15e-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e15e-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6e15e-110">Return Value</span></span>  

 <span data-ttu-id="6e15e-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="6e15e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e15e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6e15e-112">Requirements</span></span>  

 <span data-ttu-id="6e15e-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="6e15e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e15e-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6e15e-114">See also</span></span>

- [<span data-ttu-id="6e15e-115">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="6e15e-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
