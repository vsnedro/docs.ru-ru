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
ms.openlocfilehash: 60fbccabd21fb8bee118689a524efa9031bb2124
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614998"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="25b4d-102">Метод ISymUnmanagedReader::GetMethodByVersion</span><span class="sxs-lookup"><span data-stu-id="25b4d-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>
<span data-ttu-id="25b4d-103">Возвращает метод чтения символов по заданному маркеру метода и номеру версии для редактирования и копирования.</span><span class="sxs-lookup"><span data-stu-id="25b4d-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="25b4d-104">Номера версий начинаются с 1 и увеличиваются каждый раз при изменении метода в результате операции редактирования и копирования.</span><span class="sxs-lookup"><span data-stu-id="25b4d-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25b4d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25b4d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25b4d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="25b4d-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="25b4d-107">окне Токен метода.</span><span class="sxs-lookup"><span data-stu-id="25b4d-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="25b4d-108">окне Версия метода.</span><span class="sxs-lookup"><span data-stu-id="25b4d-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="25b4d-109">заполняет Указатель на возвращаемый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="25b4d-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25b4d-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="25b4d-110">Return Value</span></span>  
 <span data-ttu-id="25b4d-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="25b4d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25b4d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="25b4d-112">Requirements</span></span>  
 <span data-ttu-id="25b4d-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="25b4d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25b4d-114">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="25b4d-114">See also</span></span>

- [<span data-ttu-id="25b4d-115">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="25b4d-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
