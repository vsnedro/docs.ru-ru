---
title: Функция Верификлиенткэй (Справочник по неуправляемым API)
description: Функция Верификлиенткэй обеспечивает правильную защиту ключа клиента.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 26cffe9936f2e01078b6f54e8499b58519f1018e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729425"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="6a61d-103">Функция Верификлиенткэй</span><span class="sxs-lookup"><span data-stu-id="6a61d-103">VerifyClientKey function</span></span>

<span data-ttu-id="6a61d-104">Проверяет, что ключ клиента имеет верные параметры безопасности.</span><span class="sxs-lookup"><span data-stu-id="6a61d-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6a61d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a61d-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey();
```  

## <a name="return-value"></a><span data-ttu-id="6a61d-106">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6a61d-106">Return value</span></span>

<span data-ttu-id="6a61d-107">Если функция выполнена, возвращаемое значение равно `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="6a61d-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="6a61d-108">Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки, определенным в *файле Winerror. h*.</span><span class="sxs-lookup"><span data-stu-id="6a61d-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="6a61d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6a61d-109">Requirements</span></span>  

 <span data-ttu-id="6a61d-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a61d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a61d-111">**Заголовок:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="6a61d-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="6a61d-112">**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6a61d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a61d-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6a61d-113">See also</span></span>

- [<span data-ttu-id="6a61d-114">WMI и счетчики производительности (справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="6a61d-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
