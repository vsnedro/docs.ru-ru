---
title: Метод ISymUnmanagedWriter::UsingNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.UsingNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type:
- apiref
ms.openlocfilehash: 6404252f2c1eb14f0cd723451beb82b4c65960fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683489"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="4ffa2-102">Метод ISymUnmanagedWriter::UsingNamespace</span><span class="sxs-lookup"><span data-stu-id="4ffa2-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>

<span data-ttu-id="4ffa2-103">Указывает, что данное полное имя пространства имен используется в открытой лексической области.</span><span class="sxs-lookup"><span data-stu-id="4ffa2-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="4ffa2-104">Пространство имен будет использоваться во всех областях, наследующих от текущей открытой области.</span><span class="sxs-lookup"><span data-stu-id="4ffa2-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="4ffa2-105">Закрытие текущей области также приведет к отмене использования пространства имен.</span><span class="sxs-lookup"><span data-stu-id="4ffa2-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ffa2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ffa2-106">Syntax</span></span>  
  
```cpp  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ffa2-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ffa2-107">Parameters</span></span>  

 `fullName`  
 <span data-ttu-id="4ffa2-108">окне Указатель на полное имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="4ffa2-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ffa2-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4ffa2-109">Return Value</span></span>  

 <span data-ttu-id="4ffa2-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="4ffa2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ffa2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4ffa2-111">Requirements</span></span>  

 <span data-ttu-id="4ffa2-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="4ffa2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ffa2-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4ffa2-113">See also</span></span>

- [<span data-ttu-id="4ffa2-114">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="4ffa2-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
