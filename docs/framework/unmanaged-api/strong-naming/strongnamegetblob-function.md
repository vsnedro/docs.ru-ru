---
title: Функция StrongNameGetBlob
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
ms.openlocfilehash: 8f5cb89294004dfb1f020627ceb1edb58735f72c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732285"
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="1c339-102">Функция StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="1c339-102">StrongNameGetBlob Function</span></span>

<span data-ttu-id="1c339-103">Заполняет указанный буфер двоичным представлением исполняемого файла по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="1c339-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="1c339-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="1c339-104">This function has been deprecated.</span></span> <span data-ttu-id="1c339-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameGetBLob](../hosting/iclrstrongname-strongnamegetblob-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1c339-105">Use the [ICLRStrongName::StrongNameGetBLob](../hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c339-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c339-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c339-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="1c339-107">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="1c339-108">окне Допустимый путь к исполняемому файлу для загрузки.</span><span class="sxs-lookup"><span data-stu-id="1c339-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="1c339-109">окне Буфер, в который загружается исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="1c339-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="1c339-110">[вход, выход] Запрошенный максимальный размер (в байтах) `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="1c339-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="1c339-111">При возврате фактический размер (в байтах) для `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="1c339-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c339-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1c339-112">Return Value</span></span>  

 <span data-ttu-id="1c339-113">`true` При успешном завершении; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="1c339-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c339-114">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1c339-114">Remarks</span></span>  

 <span data-ttu-id="1c339-115">Если `StrongNameGetBlob` функция не завершается успешно, вызовите функцию [стронгнамирроринфо](strongnameerrorinfo-function.md) , чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="1c339-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c339-116">Требования</span><span class="sxs-lookup"><span data-stu-id="1c339-116">Requirements</span></span>  

 <span data-ttu-id="1c339-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c339-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c339-118">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="1c339-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1c339-119">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1c339-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1c339-120">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c339-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c339-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1c339-121">See also</span></span>

- [<span data-ttu-id="1c339-122">Метод StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="1c339-122">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="1c339-123">Метод StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="1c339-123">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="1c339-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="1c339-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
