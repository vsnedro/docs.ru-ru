---
title: Метод ISymUnmanagedSourceServerModule::GetSourceServerData
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule.GetSourceServerData
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type:
- apiref
ms.openlocfilehash: c76c8b23e707b530cbf1c28d03fbf2f84d424482
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734014"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="aea04-102">Метод ISymUnmanagedSourceServerModule::GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="aea04-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>

<span data-ttu-id="aea04-103">Возвращает данные исходного сервера для модуля.</span><span class="sxs-lookup"><span data-stu-id="aea04-103">Returns the source server data for the module.</span></span> <span data-ttu-id="aea04-104">Вызывающий объект должен освободить ресурсы с помощью `CoTaskMemFree` .</span><span class="sxs-lookup"><span data-stu-id="aea04-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aea04-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aea04-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aea04-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="aea04-106">Parameters</span></span>  

 `pDataByteCount`  
 <span data-ttu-id="aea04-107">заполняет Указатель на объект `ULONG32` , который получает размер (в байтах) данных сервера-источника.</span><span class="sxs-lookup"><span data-stu-id="aea04-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="aea04-108">заполняет Указатель на возвращаемое `pDataByteCount` значение.</span><span class="sxs-lookup"><span data-stu-id="aea04-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aea04-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="aea04-109">Return Value</span></span>  

 <span data-ttu-id="aea04-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="aea04-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aea04-111">Требования</span><span class="sxs-lookup"><span data-stu-id="aea04-111">Requirements</span></span>  

 <span data-ttu-id="aea04-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="aea04-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea04-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aea04-113">See also</span></span>

- [<span data-ttu-id="aea04-114">Интерфейс ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="aea04-114">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)
