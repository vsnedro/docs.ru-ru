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
ms.openlocfilehash: 6a7824949edc905a3edcd58f60d40f8b1a40c53c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726916"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="b59de-102">Метод ISymUnmanagedVariable::GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="b59de-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>

<span data-ttu-id="b59de-103">Возвращает тип адреса этой переменной.</span><span class="sxs-lookup"><span data-stu-id="b59de-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b59de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b59de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b59de-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b59de-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="b59de-106">заполняет Указатель на объект `ULONG32` , который получает значение.</span><span class="sxs-lookup"><span data-stu-id="b59de-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="b59de-107">Возможные значения определяются в перечислении [корсимаддркинд](corsymaddrkind-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="b59de-107">The possible values are defined in the [CorSymAddrKind](corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b59de-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b59de-108">Return Value</span></span>  

 <span data-ttu-id="b59de-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="b59de-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b59de-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b59de-110">Requirements</span></span>  

 <span data-ttu-id="b59de-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="b59de-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b59de-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b59de-112">See also</span></span>

- [<span data-ttu-id="b59de-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="b59de-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
