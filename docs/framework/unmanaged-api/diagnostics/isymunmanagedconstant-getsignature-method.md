---
title: Метод ISymUnmanagedConstant::GetSignature
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type:
- apiref
ms.openlocfilehash: 4436e4528c1dc486eb5c443c5a9467ac69a26c7d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706935"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="43201-102">Метод ISymUnmanagedConstant::GetSignature</span><span class="sxs-lookup"><span data-stu-id="43201-102">ISymUnmanagedConstant::GetSignature Method</span></span>

<span data-ttu-id="43201-103">Возвращает сигнатуру константы.</span><span class="sxs-lookup"><span data-stu-id="43201-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43201-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43201-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43201-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="43201-105">Parameters</span></span>  

 `cSig`  
 <span data-ttu-id="43201-106">окне Длина буфера, `pcSig` на который указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="43201-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="43201-107">заполняет Указатель на объект `ULONG32` , который получает размер (в символах) буфера, необходимого для хранения подписи.</span><span class="sxs-lookup"><span data-stu-id="43201-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="43201-108">заполняет Буфер, в котором хранится подпись.</span><span class="sxs-lookup"><span data-stu-id="43201-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43201-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="43201-109">Return Value</span></span>  

 <span data-ttu-id="43201-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="43201-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43201-111">Требования</span><span class="sxs-lookup"><span data-stu-id="43201-111">Requirements</span></span>  

 <span data-ttu-id="43201-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="43201-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43201-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="43201-113">See also</span></span>

- [<span data-ttu-id="43201-114">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="43201-114">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="43201-115">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="43201-115">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="43201-116">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="43201-116">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)
