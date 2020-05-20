---
title: Метод IDebugAutoAttach::AutoAttach
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
ms.openlocfilehash: aae03b0dc76639c50f4615d41eef73990226b5f7
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442128"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="a8121-102">Метод IDebugAutoAttach::AutoAttach</span><span class="sxs-lookup"><span data-stu-id="a8121-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="a8121-103">Выполняет вызванное сервером автоматическое присоединение отладчика.</span><span class="sxs-lookup"><span data-stu-id="a8121-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8121-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8121-104">Syntax</span></span>  
  
```cpp  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8121-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a8121-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="a8121-106">окне Всегда имеет значение `GUID_NULL` .</span><span class="sxs-lookup"><span data-stu-id="a8121-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="a8121-107">окне Идентификатор процесса, обычно полученный с помощью `GetCurrentProcessId` функции.</span><span class="sxs-lookup"><span data-stu-id="a8121-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="a8121-108">окне Тип программы: `AUTOATTACH_PROGRAM_WIN32` , `AUTOATTACH_PROGRAM_COMPLUS` или `AUTOATTACH_PROGRAM_UNKNOWN` .</span><span class="sxs-lookup"><span data-stu-id="a8121-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="a8121-109">окне Идентификатор программы.</span><span class="sxs-lookup"><span data-stu-id="a8121-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="a8121-110">окне Строка, передаваемая командой Debug.</span><span class="sxs-lookup"><span data-stu-id="a8121-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8121-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a8121-111">Return Value</span></span>  
 <span data-ttu-id="a8121-112">S_OK, если метод выполнен.</span><span class="sxs-lookup"><span data-stu-id="a8121-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8121-113">Требования</span><span class="sxs-lookup"><span data-stu-id="a8121-113">Requirements</span></span>  
 <span data-ttu-id="a8121-114">**Заголовок:** Дбгаутоаттач. h</span><span class="sxs-lookup"><span data-stu-id="a8121-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8121-115">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="a8121-115">See also</span></span>

- [<span data-ttu-id="a8121-116">Интерфейс IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="a8121-116">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)
