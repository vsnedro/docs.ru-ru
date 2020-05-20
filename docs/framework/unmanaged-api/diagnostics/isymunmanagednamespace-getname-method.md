---
title: Метод ISymUnmanagedNamespace::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
ms.openlocfilehash: 84b2f1226c84713483499c7ff777838058cb0f95
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615115"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="a3e48-102">Метод ISymUnmanagedNamespace::GetName</span><span class="sxs-lookup"><span data-stu-id="a3e48-102">ISymUnmanagedNamespace::GetName Method</span></span>
<span data-ttu-id="a3e48-103">Возвращает имя этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a3e48-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3e48-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a3e48-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3e48-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a3e48-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="a3e48-106">окне Значение типа `ULONG32` , указывающее размер `szName` буфера.</span><span class="sxs-lookup"><span data-stu-id="a3e48-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a3e48-107">заполняет Указатель на объект `ULONG32` , который получает размер (в символах) буфера, необходимого для хранения имени пространства имен, включая завершение значения NULL.</span><span class="sxs-lookup"><span data-stu-id="a3e48-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="a3e48-108">заполняет Указатель на буфер, содержащий имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a3e48-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3e48-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a3e48-109">Return Value</span></span>  
 <span data-ttu-id="a3e48-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="a3e48-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3e48-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a3e48-111">Requirements</span></span>  
 <span data-ttu-id="a3e48-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="a3e48-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3e48-113">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="a3e48-113">See also</span></span>

- [<span data-ttu-id="a3e48-114">Интерфейс ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="a3e48-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
