---
title: Указатель функции LPOVERLAPPED_COMPLETION_ROUTINE
ms.date: 03/30/2017
api_name:
- LPOVERLAPPED_COMPLETION_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type:
- apiref
ms.openlocfilehash: a3a45a13073cf422064d28554a274e068db6f517
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727514"
---
# <a name="lpoverlapped_completion_routine-function-pointer"></a><span data-ttu-id="226de-102">Указатель функции LPOVERLAPPED_COMPLETION_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="226de-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>

<span data-ttu-id="226de-103">Указывает на функцию, которая уведомляет узел при завершении перекрытия (асинхронного) ввода-вывода на устройство.</span><span class="sxs-lookup"><span data-stu-id="226de-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="226de-104">Этот указатель функции является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="226de-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="226de-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="226de-105">Syntax</span></span>  
  
```cpp  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="226de-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="226de-106">Parameters</span></span>  

 `dwErrorCode`  
 <span data-ttu-id="226de-107">окне Значение, которое является кодом ошибки, если устройство было закрыто; в противном случае это значение равно нулю.</span><span class="sxs-lookup"><span data-stu-id="226de-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="226de-108">Закрытие устройства приводит к немедленному завершению операций ввода-вывода на устройстве.</span><span class="sxs-lookup"><span data-stu-id="226de-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="226de-109">окне Число байтов, передаваемых операцией ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="226de-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="226de-110">окне Указатель на структуру, содержащую сведения, используемые для завершения запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="226de-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="226de-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="226de-111">Remarks</span></span>  

 <span data-ttu-id="226de-112">Функция, к которой `LPOVERLAPPED_COMPLETION_ROUTINE` points является функцией обратного вызова и должна быть реализована модулем записи размещающего приложения.</span><span class="sxs-lookup"><span data-stu-id="226de-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="226de-113">Функция обратного вызова позволяет узлу обработать завершенный запрос ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="226de-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="226de-114">Требования</span><span class="sxs-lookup"><span data-stu-id="226de-114">Requirements</span></span>  

 <span data-ttu-id="226de-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="226de-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="226de-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="226de-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="226de-117">**Библиотека:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="226de-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="226de-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="226de-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="226de-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="226de-119">See also</span></span>

- [<span data-ttu-id="226de-120">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="226de-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
