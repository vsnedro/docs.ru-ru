---
title: Метод ICorDebugRemoteTarget::GetHostName
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
ms.openlocfilehash: 020724c422af7cba0165e6f37d0eacb7742153ec
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379274"
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="3eb0e-102">Метод ICorDebugRemoteTarget::GetHostName</span><span class="sxs-lookup"><span data-stu-id="3eb0e-102">ICorDebugRemoteTarget::GetHostName Method</span></span>
<span data-ttu-id="3eb0e-103">Возвращает полное доменное имя или IPv4-адрес целевого компьютера удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="3eb0e-103">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="3eb0e-104">В настоящее время IPV6 не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3eb0e-104">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eb0e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3eb0e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a><span data-ttu-id="3eb0e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3eb0e-106">Parameters</span></span>  
 `cchHostName`  
 <span data-ttu-id="3eb0e-107">окне Размер буфера (в символах) `szHostName` .</span><span class="sxs-lookup"><span data-stu-id="3eb0e-107">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="3eb0e-108">Если этот параметр равен 0 (нулю), он `szHostName` должен иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="3eb0e-108">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="3eb0e-109">заполняет Количество символов, включая знак завершения null, в имени узла или IP-адресе.</span><span class="sxs-lookup"><span data-stu-id="3eb0e-109">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="3eb0e-110">Этот параметр может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="3eb0e-110">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="3eb0e-111">заполняет Буфер, содержащий имя узла или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="3eb0e-111">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3eb0e-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3eb0e-112">Return Value</span></span>  
 <span data-ttu-id="3eb0e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="3eb0e-113">S_OK</span></span>  
 <span data-ttu-id="3eb0e-114">Имя узла или IP-адрес успешно возвращены.</span><span class="sxs-lookup"><span data-stu-id="3eb0e-114">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="3eb0e-115">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="3eb0e-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="3eb0e-116">Не удалось вернуть имя узла или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="3eb0e-116">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3eb0e-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="3eb0e-117">Remarks</span></span>  
 <span data-ttu-id="3eb0e-118">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="3eb0e-118">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="3eb0e-119">Он должен следовать парадигме нескольких вызовов: при первом вызове вызывающий объект передает значение NULL и `cchHostName` в `szHostName` , и `pcchHostName` возвращает размер требуемого буфера.</span><span class="sxs-lookup"><span data-stu-id="3eb0e-119">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer.</span></span> <span data-ttu-id="3eb0e-120">При втором вызове передается размер, который был ранее возвращен `cchHostName` , и передается буфер соответствующего размера `szHostName` .</span><span class="sxs-lookup"><span data-stu-id="3eb0e-120">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eb0e-121">Требования</span><span class="sxs-lookup"><span data-stu-id="3eb0e-121">Requirements</span></span>  
 <span data-ttu-id="3eb0e-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3eb0e-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eb0e-123">**Заголовок:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="3eb0e-123">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="3eb0e-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3eb0e-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3eb0e-125">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="3eb0e-125">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb0e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="3eb0e-126">See also</span></span>

- [<span data-ttu-id="3eb0e-127">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="3eb0e-127">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="3eb0e-128">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="3eb0e-128">ICorDebug Interface</span></span>](icordebug-interface.md)
