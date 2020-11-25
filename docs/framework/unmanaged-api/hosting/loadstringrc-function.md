---
title: Функция LoadStringRC
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
ms.openlocfilehash: 16f95f8fce20f2cf46d4cda214e4494bd288bf60
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727553"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="16414-102">Функция LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="16414-102">LoadStringRC Function</span></span>

<span data-ttu-id="16414-103">Преобразует значение HRESULT в сообщение об ошибке с помощью языка и региональных параметров по умолчанию текущего потока.</span><span class="sxs-lookup"><span data-stu-id="16414-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="16414-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="16414-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16414-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16414-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16414-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="16414-106">Parameters</span></span>  

 `iResourceID`  
 <span data-ttu-id="16414-107">[in] Значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="16414-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="16414-108">заполняет Буфер, содержащий сообщение об ошибке после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="16414-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="16414-109">окне Размер буфера сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="16414-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="16414-110">окне Игнорируют.</span><span class="sxs-lookup"><span data-stu-id="16414-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16414-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="16414-111">Return Value</span></span>  

 <span data-ttu-id="16414-112">Этот метод возвращает коды стандартных ошибок модели COM, как определено в файле WinError. h, в дополнение к следующим значениям.</span><span class="sxs-lookup"><span data-stu-id="16414-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="16414-113">Код возврата</span><span class="sxs-lookup"><span data-stu-id="16414-113">Return code</span></span>|<span data-ttu-id="16414-114">Описание</span><span class="sxs-lookup"><span data-stu-id="16414-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="16414-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="16414-115">S_OK</span></span>|<span data-ttu-id="16414-116">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="16414-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="16414-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="16414-117">E_INVALIDARG</span></span>|<span data-ttu-id="16414-118">`szBuffer` имеет значение null или `iMax` равно нулю (0).</span><span class="sxs-lookup"><span data-stu-id="16414-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16414-119">Комментарии</span><span class="sxs-lookup"><span data-stu-id="16414-119">Remarks</span></span>  

 <span data-ttu-id="16414-120">Если метод не завершается успешно, `szBuffer` содержит пустую строку.</span><span class="sxs-lookup"><span data-stu-id="16414-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16414-121">Требования</span><span class="sxs-lookup"><span data-stu-id="16414-121">Requirements</span></span>  

 <span data-ttu-id="16414-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16414-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16414-123">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="16414-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16414-124">**Библиотека:** MSCorEE.dll и Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="16414-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="16414-125">Используйте MSCorEE.dll вместо Mscorwks.dll, чтобы убедиться в правильности целевой версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="16414-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="16414-126">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16414-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16414-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="16414-127">See also</span></span>

- [<span data-ttu-id="16414-128">Функция LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="16414-128">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)
- [<span data-ttu-id="16414-129">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="16414-129">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
