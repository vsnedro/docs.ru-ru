---
title: Метод ISymUnmanagedConstant::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
ms.openlocfilehash: 2dd70693528904459a34689dbad944c65c971254
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441647"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="31058-102">Метод ISymUnmanagedConstant::GetName</span><span class="sxs-lookup"><span data-stu-id="31058-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="31058-103">Возвращает имя константы.</span><span class="sxs-lookup"><span data-stu-id="31058-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31058-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31058-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31058-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="31058-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="31058-106">окне Длина буфера, `szName` на который указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="31058-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="31058-107">заполняет Указатель на объект `ULONG32` , который получает размер (в символах) буфера, необходимого для хранения имени, включая завершение нулевого значения.</span><span class="sxs-lookup"><span data-stu-id="31058-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="31058-108">заполняет Буфер, в котором хранится имя.</span><span class="sxs-lookup"><span data-stu-id="31058-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31058-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="31058-109">Return Value</span></span>  
 <span data-ttu-id="31058-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="31058-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31058-111">Требования</span><span class="sxs-lookup"><span data-stu-id="31058-111">Requirements</span></span>  
 <span data-ttu-id="31058-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="31058-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31058-113">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="31058-113">See also</span></span>

- [<span data-ttu-id="31058-114">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="31058-114">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="31058-115">Метод GetSignature</span><span class="sxs-lookup"><span data-stu-id="31058-115">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="31058-116">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="31058-116">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)
