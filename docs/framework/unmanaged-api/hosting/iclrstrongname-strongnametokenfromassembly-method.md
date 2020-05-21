---
title: Метод ICLRStrongName::StrongNameTokenFromAssembly
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type:
- apiref
ms.openlocfilehash: e71fcf80b51edc318bbc7d81bb277c614184ee55
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762517"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="a5ba8-102">Метод ICLRStrongName::StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="a5ba8-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="a5ba8-103">Создает маркер строгого имени из указанного файла сборки.</span><span class="sxs-lookup"><span data-stu-id="a5ba8-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5ba8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5ba8-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5ba8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5ba8-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="a5ba8-106">окне Путь к переносимому исполняемому файлу (PE) для сборки.</span><span class="sxs-lookup"><span data-stu-id="a5ba8-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="a5ba8-107">заполняет Возвращенный маркер строгого имени.</span><span class="sxs-lookup"><span data-stu-id="a5ba8-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="a5ba8-108">заполняет Размер (в байтах) маркера строгого имени.</span><span class="sxs-lookup"><span data-stu-id="a5ba8-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5ba8-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a5ba8-109">Return Value</span></span>  
 <span data-ttu-id="a5ba8-110">`S_OK`значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="a5ba8-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5ba8-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a5ba8-111">Remarks</span></span>  
 <span data-ttu-id="a5ba8-112">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="a5ba8-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="a5ba8-113">Маркер представляет собой 64-разрядный хэш, созданный из открытого ключа, используемого для подписания сборки.</span><span class="sxs-lookup"><span data-stu-id="a5ba8-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="a5ba8-114">Токен является частью строгого имени сборки и может быть считан из метаданных сборки.</span><span class="sxs-lookup"><span data-stu-id="a5ba8-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="a5ba8-115">После создания маркера следует вызвать метод [метод iclrstrongname:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) , чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="a5ba8-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5ba8-116">Требования</span><span class="sxs-lookup"><span data-stu-id="a5ba8-116">Requirements</span></span>  
 <span data-ttu-id="a5ba8-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5ba8-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5ba8-118">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="a5ba8-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a5ba8-119">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a5ba8-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5ba8-120">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5ba8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ba8-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a5ba8-121">See also</span></span>

- [<span data-ttu-id="a5ba8-122">Метод StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="a5ba8-122">StrongNameTokenFromAssemblyEx Method</span></span>](iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="a5ba8-123">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a5ba8-123">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
