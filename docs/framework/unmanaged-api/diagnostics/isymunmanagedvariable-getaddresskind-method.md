---
title: Метод ISymUnmanagedVariable::GetAddressKind
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressKind
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressKind
helpviewer_keywords:
- GetAddressKind method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressKind method [.NET Framework debugging]
ms.assetid: a71563c0-62f2-4eb4-970c-825d61827613
topic_type:
- apiref
ms.openlocfilehash: 093c5e3e64395c8946acd9201990d132e8111fc7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610591"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="f3670-102">Метод ISymUnmanagedVariable::GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="f3670-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="f3670-103">Возвращает тип адреса этой переменной.</span><span class="sxs-lookup"><span data-stu-id="f3670-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3670-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3670-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3670-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3670-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f3670-106">заполняет Указатель на объект `ULONG32` , который получает значение.</span><span class="sxs-lookup"><span data-stu-id="f3670-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="f3670-107">Возможные значения определяются в перечислении [корсимаддркинд](corsymaddrkind-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="f3670-107">The possible values are defined in the [CorSymAddrKind](corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3670-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f3670-108">Return Value</span></span>  
 <span data-ttu-id="f3670-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="f3670-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3670-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f3670-110">Requirements</span></span>  
 <span data-ttu-id="f3670-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="f3670-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3670-112">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="f3670-112">See also</span></span>

- [<span data-ttu-id="f3670-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="f3670-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
