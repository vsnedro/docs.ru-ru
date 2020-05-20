---
title: Метод ISymUnmanagedVariable::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type:
- apiref
ms.openlocfilehash: b48d131fa99b65d38856d2b635bf59145db9157e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615245"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="41a09-102">Метод ISymUnmanagedVariable::GetName</span><span class="sxs-lookup"><span data-stu-id="41a09-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="41a09-103">Возвращает имя этой переменной.</span><span class="sxs-lookup"><span data-stu-id="41a09-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41a09-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41a09-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41a09-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="41a09-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="41a09-106">окне Длина буфера, `pcchName` на который указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="41a09-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="41a09-107">заполняет Указатель на объект `ULONG32` , который получает размер (в символах) буфера, необходимого для хранения имени, включая завершение нулевого значения.</span><span class="sxs-lookup"><span data-stu-id="41a09-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="41a09-108">заполняет Буфер, в котором хранится имя.</span><span class="sxs-lookup"><span data-stu-id="41a09-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41a09-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="41a09-109">Return Value</span></span>  
 <span data-ttu-id="41a09-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="41a09-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41a09-111">Требования</span><span class="sxs-lookup"><span data-stu-id="41a09-111">Requirements</span></span>  
 <span data-ttu-id="41a09-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="41a09-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a09-113">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="41a09-113">See also</span></span>

- [<span data-ttu-id="41a09-114">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="41a09-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
