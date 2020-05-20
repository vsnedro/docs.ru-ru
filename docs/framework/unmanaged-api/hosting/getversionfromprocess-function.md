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
ms.openlocfilehash: fbaf45da0902ded8a2f7bf0d470aaed3b5f531aa
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617130"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="c3af9-102">Функция GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="c3af9-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="c3af9-103">Возвращает номер версии общеязыковой среды выполнения (CLR), связанной с указанным обработчиком процесса.</span><span class="sxs-lookup"><span data-stu-id="c3af9-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="c3af9-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c3af9-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3af9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3af9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3af9-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c3af9-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="c3af9-107">окне Обработчик процесса.</span><span class="sxs-lookup"><span data-stu-id="c3af9-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="c3af9-108">заполняет Буфер, содержащий строку номера версии после успешного завершения метода.</span><span class="sxs-lookup"><span data-stu-id="c3af9-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="c3af9-109">окне Длина буфера версии.</span><span class="sxs-lookup"><span data-stu-id="c3af9-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="c3af9-110">заполняет Указатель на длину строки номера версии.</span><span class="sxs-lookup"><span data-stu-id="c3af9-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3af9-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c3af9-111">Return Value</span></span>  
 <span data-ttu-id="c3af9-112">Этот метод возвращает коды стандартных ошибок модели COM, как определено в файле WinError. h, в дополнение к следующим значениям.</span><span class="sxs-lookup"><span data-stu-id="c3af9-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="c3af9-113">Код возврата</span><span class="sxs-lookup"><span data-stu-id="c3af9-113">Return code</span></span>|<span data-ttu-id="c3af9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c3af9-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c3af9-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3af9-115">S_OK</span></span>|<span data-ttu-id="c3af9-116">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="c3af9-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="c3af9-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c3af9-117">E_INVALIDARG</span></span>|<span data-ttu-id="c3af9-118">`pVersion`имеет значение NULL и не `cchBuffer` имеет значение null, или наоборот.</span><span class="sxs-lookup"><span data-stu-id="c3af9-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="c3af9-119">-или-</span><span class="sxs-lookup"><span data-stu-id="c3af9-119">-or-</span></span><br /><br /> <span data-ttu-id="c3af9-120">`hProcess`не является допустимым маркером для процесса.</span><span class="sxs-lookup"><span data-stu-id="c3af9-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="c3af9-121">-или-</span><span class="sxs-lookup"><span data-stu-id="c3af9-121">-or-</span></span><br /><br /> <span data-ttu-id="c3af9-122">Среда CLR не загружена.</span><span class="sxs-lookup"><span data-stu-id="c3af9-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="c3af9-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="c3af9-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="c3af9-124">`cchBuffer`параметр имеет значение null или меньше длины строки версии.</span><span class="sxs-lookup"><span data-stu-id="c3af9-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="c3af9-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="c3af9-125">E_NOTIMPL</span></span>|<span data-ttu-id="c3af9-126">Этот метод недоступен в операционной системе Microsoft Windows 95, Microsoft Windows 98 или Microsoft Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="c3af9-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3af9-127">Требования</span><span class="sxs-lookup"><span data-stu-id="c3af9-127">Requirements</span></span>  
 <span data-ttu-id="c3af9-128">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3af9-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3af9-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c3af9-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3af9-130">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c3af9-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3af9-131">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3af9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3af9-132">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="c3af9-132">See also</span></span>

- [<span data-ttu-id="c3af9-133">Функция GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="c3af9-133">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="c3af9-134">Функция GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="c3af9-134">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)
- [<span data-ttu-id="c3af9-135">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="c3af9-135">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
