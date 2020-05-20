---
title: Метод ISymUnmanagedVariable::GetSignature
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
ms.openlocfilehash: a3ec0af33f3f1201ce2f6b62291dfc67696fecab
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610448"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="f08ac-102">Метод ISymUnmanagedVariable::GetSignature</span><span class="sxs-lookup"><span data-stu-id="f08ac-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="f08ac-103">Возвращает сигнатуру этой переменной.</span><span class="sxs-lookup"><span data-stu-id="f08ac-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f08ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f08ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f08ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f08ac-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="f08ac-106">окне Длина буфера, на который указывает `sig` параметр.</span><span class="sxs-lookup"><span data-stu-id="f08ac-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="f08ac-107">заполняет Указатель на объект `ULONG32` , который получает размер (в символах) буфера, необходимого для хранения подписи.</span><span class="sxs-lookup"><span data-stu-id="f08ac-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="f08ac-108">заполняет Буфер, в котором хранится подпись.</span><span class="sxs-lookup"><span data-stu-id="f08ac-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f08ac-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f08ac-109">Return Value</span></span>  
 <span data-ttu-id="f08ac-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="f08ac-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f08ac-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f08ac-111">Requirements</span></span>  
 <span data-ttu-id="f08ac-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="f08ac-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f08ac-113">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="f08ac-113">See also</span></span>

- [<span data-ttu-id="f08ac-114">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="f08ac-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
