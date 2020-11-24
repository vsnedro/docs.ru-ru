---
title: Функция CreateHistoryReader
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
ms.openlocfilehash: 9dae3f1403d33aaf3cfb87d17856640548a90b4d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688980"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="c0981-102">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="c0981-102">CreateHistoryReader Function</span></span>

<span data-ttu-id="c0981-103">Создает средство чтения журнала для указанного файла.</span><span class="sxs-lookup"><span data-stu-id="c0981-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0981-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0981-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0981-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0981-105">Parameters</span></span>  

 `wzFilePath`  
 <span data-ttu-id="c0981-106">окне Путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="c0981-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="c0981-107">заполняет При успешном завершении содержит указатель на средство чтения журнала.</span><span class="sxs-lookup"><span data-stu-id="c0981-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0981-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c0981-108">Return Value</span></span>  

 <span data-ttu-id="c0981-109">Этот метод возвращает стандартные коды ошибок COM, определенные в файле WinError. h, а также значения, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c0981-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="c0981-110">Код возврата</span><span class="sxs-lookup"><span data-stu-id="c0981-110">Return code</span></span>|<span data-ttu-id="c0981-111">Описание</span><span class="sxs-lookup"><span data-stu-id="c0981-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c0981-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c0981-112">S_OK</span></span>|<span data-ttu-id="c0981-113">Указывает, что метод успешно завершен.</span><span class="sxs-lookup"><span data-stu-id="c0981-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="c0981-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c0981-114">E_INVALIDARG</span></span>|<span data-ttu-id="c0981-115">Указывает, что `wzFilePath` или `ppHistoryReader` задана пустая ссылка.</span><span class="sxs-lookup"><span data-stu-id="c0981-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0981-116">Требования</span><span class="sxs-lookup"><span data-stu-id="c0981-116">Requirements</span></span>  

 <span data-ttu-id="c0981-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0981-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0981-118">**Библиотека:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="c0981-118">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="c0981-119">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0981-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0981-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c0981-120">See also</span></span>

- [<span data-ttu-id="c0981-121">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="c0981-121">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
