---
title: Метод ISymUnmanagedENCUpdate::GetLocalVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
ms.openlocfilehash: 9e907450b4ae985ee30d9958eec8baba797b495a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728606"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="5b48f-102">Метод ISymUnmanagedENCUpdate::GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="5b48f-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>

<span data-ttu-id="5b48f-103">Возвращает локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="5b48f-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b48f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b48f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b48f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b48f-105">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="5b48f-106">окне Маркер метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="5b48f-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="5b48f-107">окне Значение типа `ULONG` , указывающее размер `rgLocals` параметра.</span><span class="sxs-lookup"><span data-stu-id="5b48f-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="5b48f-108">заполняет Возвращаемый массив экземпляров [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5b48f-108">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5b48f-109">заполняет Указатель на объект `ULONG` , который получает размер `rgLocals` буфера, необходимого для хранения локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="5b48f-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b48f-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5b48f-110">Return Value</span></span>  

 <span data-ttu-id="5b48f-111">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="5b48f-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b48f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5b48f-112">Requirements</span></span>  

 <span data-ttu-id="5b48f-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="5b48f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b48f-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5b48f-114">See also</span></span>

- [<span data-ttu-id="5b48f-115">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="5b48f-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
