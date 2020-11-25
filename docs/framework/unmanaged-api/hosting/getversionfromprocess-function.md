---
title: Функция GetVersionFromProcess
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
ms.openlocfilehash: da0d159da6eef7745c1fa7f7320d5e1355f6e413
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721885"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="2130c-102">Функция GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="2130c-102">GetVersionFromProcess Function</span></span>

<span data-ttu-id="2130c-103">Возвращает номер версии общеязыковой среды выполнения (CLR), связанной с указанным обработчиком процесса.</span><span class="sxs-lookup"><span data-stu-id="2130c-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="2130c-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="2130c-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2130c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2130c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2130c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2130c-106">Parameters</span></span>  

 `hProcess`  
 <span data-ttu-id="2130c-107">окне Обработчик процесса.</span><span class="sxs-lookup"><span data-stu-id="2130c-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="2130c-108">заполняет Буфер, содержащий строку номера версии после успешного завершения метода.</span><span class="sxs-lookup"><span data-stu-id="2130c-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="2130c-109">окне Длина буфера версии.</span><span class="sxs-lookup"><span data-stu-id="2130c-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="2130c-110">заполняет Указатель на длину строки номера версии.</span><span class="sxs-lookup"><span data-stu-id="2130c-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2130c-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2130c-111">Return Value</span></span>  

 <span data-ttu-id="2130c-112">Этот метод возвращает коды стандартных ошибок модели COM, как определено в файле WinError. h, в дополнение к следующим значениям.</span><span class="sxs-lookup"><span data-stu-id="2130c-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="2130c-113">Код возврата</span><span class="sxs-lookup"><span data-stu-id="2130c-113">Return code</span></span>|<span data-ttu-id="2130c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2130c-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="2130c-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="2130c-115">S_OK</span></span>|<span data-ttu-id="2130c-116">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="2130c-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="2130c-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2130c-117">E_INVALIDARG</span></span>|<span data-ttu-id="2130c-118">`pVersion` имеет значение NULL и не `cchBuffer` имеет значение null, или наоборот.</span><span class="sxs-lookup"><span data-stu-id="2130c-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="2130c-119">-или-</span><span class="sxs-lookup"><span data-stu-id="2130c-119">-or-</span></span><br /><br /> <span data-ttu-id="2130c-120">`hProcess` не является допустимым маркером для процесса.</span><span class="sxs-lookup"><span data-stu-id="2130c-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="2130c-121">-или-</span><span class="sxs-lookup"><span data-stu-id="2130c-121">-or-</span></span><br /><br /> <span data-ttu-id="2130c-122">Среда CLR не загружена.</span><span class="sxs-lookup"><span data-stu-id="2130c-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="2130c-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="2130c-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="2130c-124">`cchBuffer` параметр имеет значение null или меньше длины строки версии.</span><span class="sxs-lookup"><span data-stu-id="2130c-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="2130c-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="2130c-125">E_NOTIMPL</span></span>|<span data-ttu-id="2130c-126">Этот метод недоступен в операционной системе Microsoft Windows 95, Microsoft Windows 98 или Microsoft Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="2130c-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2130c-127">Требования</span><span class="sxs-lookup"><span data-stu-id="2130c-127">Requirements</span></span>  

 <span data-ttu-id="2130c-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2130c-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2130c-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2130c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2130c-130">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2130c-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2130c-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2130c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2130c-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2130c-132">See also</span></span>

- [<span data-ttu-id="2130c-133">Функция GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="2130c-133">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="2130c-134">Функция GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="2130c-134">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)
- [<span data-ttu-id="2130c-135">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="2130c-135">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
