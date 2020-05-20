---
title: Функция GetRequestedRuntimeVersion
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
ms.openlocfilehash: b7a38d28b55842e9358bd9c7019b84c529526613
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617169"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="f768d-102">Функция GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="f768d-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="f768d-103">Возвращает номер версии общеязыковой среды выполнения (CLR), запрошенной указанным приложением.</span><span class="sxs-lookup"><span data-stu-id="f768d-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="f768d-104">Если эта версия не установлена, возвращает последнюю версию, установленную до запрошенной версии.</span><span class="sxs-lookup"><span data-stu-id="f768d-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="f768d-105">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f768d-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f768d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f768d-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f768d-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="f768d-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="f768d-108">окне Имя приложения.</span><span class="sxs-lookup"><span data-stu-id="f768d-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="f768d-109">заполняет Буфер, содержащий строку номера версии после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="f768d-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="f768d-110">окне Длина буфера версии.</span><span class="sxs-lookup"><span data-stu-id="f768d-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="f768d-111">заполняет Указатель на длину строки номера версии.</span><span class="sxs-lookup"><span data-stu-id="f768d-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f768d-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f768d-112">Return Value</span></span>  
 <span data-ttu-id="f768d-113">Этот метод возвращает коды стандартных ошибок модели COM, как определено в файле WinError. h, в дополнение к следующим значениям.</span><span class="sxs-lookup"><span data-stu-id="f768d-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="f768d-114">Код возврата</span><span class="sxs-lookup"><span data-stu-id="f768d-114">Return code</span></span>|<span data-ttu-id="f768d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f768d-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f768d-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="f768d-116">S_OK</span></span>|<span data-ttu-id="f768d-117">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="f768d-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="f768d-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f768d-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f768d-119">Буфер версии недостаточно велик для хранения строки версии.</span><span class="sxs-lookup"><span data-stu-id="f768d-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="f768d-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f768d-120">E_POINTER</span></span>|<span data-ttu-id="f768d-121">Параметр `pdwLength` имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="f768d-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f768d-122">Требования</span><span class="sxs-lookup"><span data-stu-id="f768d-122">Requirements</span></span>  
 <span data-ttu-id="f768d-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f768d-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f768d-124">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f768d-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f768d-125">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f768d-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f768d-126">**.NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f768d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f768d-127">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="f768d-127">See also</span></span>

- [<span data-ttu-id="f768d-128">Функция GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="f768d-128">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="f768d-129">Функция GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="f768d-129">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)
- [<span data-ttu-id="f768d-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="f768d-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
