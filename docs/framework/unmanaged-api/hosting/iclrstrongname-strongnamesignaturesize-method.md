---
title: Метод ICLRStrongName::StrongNameSignatureSize
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
ms.openlocfilehash: edce771b3c36f2c56637aa2a21fe524be0ae12c8
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763024"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="46f59-102">Метод ICLRStrongName::StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="46f59-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="46f59-103">Возвращает размер подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="46f59-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="46f59-104">Этот метод обычно используется компиляторами для определения объема пространства, резервируемого в файле при создании сборки с отложенной подписью.</span><span class="sxs-lookup"><span data-stu-id="46f59-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46f59-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46f59-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="46f59-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="46f59-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="46f59-107">окне Структура типа [публиккэйблоб](../strong-naming/publickeyblob-structure.md) , содержащая открытую часть пары ключей, используемую для создания подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="46f59-107">[in] A structure of type [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="46f59-108">окне Размер (в байтах) `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="46f59-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="46f59-109">окне Число байтов, необходимое для хранения подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="46f59-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46f59-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="46f59-110">Return Value</span></span>  
 <span data-ttu-id="46f59-111">`S_OK`значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="46f59-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46f59-112">Требования</span><span class="sxs-lookup"><span data-stu-id="46f59-112">Requirements</span></span>  
 <span data-ttu-id="46f59-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46f59-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46f59-114">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="46f59-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="46f59-115">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="46f59-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46f59-116">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46f59-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46f59-117">См. также</span><span class="sxs-lookup"><span data-stu-id="46f59-117">See also</span></span>

- [<span data-ttu-id="46f59-118">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="46f59-118">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
