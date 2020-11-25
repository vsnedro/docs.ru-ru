---
title: Метод StrongNameGetPublicKeyEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameGetPublicKeyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type:
- apiref
ms.openlocfilehash: 8cc28d9ccd40c65d225a96b269562c9d3dfa2124
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729893"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="11489-102">Метод StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="11489-102">StrongNameGetPublicKeyEx Method</span></span>

<span data-ttu-id="11489-103">Получает открытый ключ из пары открытого и закрытого ключей и задает алгоритм хеширования и алгоритм подписи.</span><span class="sxs-lookup"><span data-stu-id="11489-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11489-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11489-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11489-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11489-105">Parameters</span></span>  

 `pwzKeyContainer`  
 <span data-ttu-id="11489-106">окне Имя контейнера ключей, содержащего пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="11489-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="11489-107">Если `pbKeyBlob` параметр имеет значение null, `szKeyContainer` необходимо указать допустимый контейнер в поставщике служб шифрования (CSP).</span><span class="sxs-lookup"><span data-stu-id="11489-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="11489-108">В этом случае `StrongNameGetPublicKeyEx` метод извлекает открытый ключ из пары ключей, хранящихся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="11489-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="11489-109">Если значение не равно `pbKeyBlob` null, предполагается, что пара ключей содержится в большом двоичном объекте Key (BLOB).</span><span class="sxs-lookup"><span data-stu-id="11489-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="11489-110">Ключи должны состоять из 1024-разрядных ключей подписывания Ривест-Шамир-Адельман (RSA).</span><span class="sxs-lookup"><span data-stu-id="11489-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="11489-111">В настоящее время не поддерживаются никакие другие типы ключей.</span><span class="sxs-lookup"><span data-stu-id="11489-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="11489-112">окне Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="11489-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="11489-113">Эта пара имеет формат, созданный `CryptExportKey` функцией Win32.</span><span class="sxs-lookup"><span data-stu-id="11489-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="11489-114">Если аргумент `pbKeyBlob` имеет значение null, предполагается, что контейнер ключей, заданный параметром, `szKeyContainer` содержит пару ключей.</span><span class="sxs-lookup"><span data-stu-id="11489-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="11489-115">окне Размер (в байтах) `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="11489-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="11489-116">заполняет Возвращенный большой двоичный объект открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="11489-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="11489-117">`ppbPublicKeyBlob`Параметр выделяется средой CLR и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="11489-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="11489-118">Вызывающий объект должен освободить память с помощью метода [метод iclrstrongname:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="11489-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="11489-119">заполняет Размер возвращенного большого двоичного объекта открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="11489-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="11489-120">окне Хэш-алгоритм сборки.</span><span class="sxs-lookup"><span data-stu-id="11489-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="11489-121">Список допустимых значений см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="11489-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="11489-122">окне Зарезервировано для будущего использования; по умолчанию принимает значение null.</span><span class="sxs-lookup"><span data-stu-id="11489-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11489-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="11489-123">Return Value</span></span>  

 <span data-ttu-id="11489-124">`S_OK` значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="11489-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11489-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="11489-125">Remarks</span></span>  

 <span data-ttu-id="11489-126">Открытый ключ содержится в структуре [публиккэйблоб](../strong-naming/publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="11489-126">The public key is contained in a [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11489-127">Комментарии</span><span class="sxs-lookup"><span data-stu-id="11489-127">Remarks</span></span>  

 <span data-ttu-id="11489-128">В следующей таблице показан набор допустимых значений для `uHashAlgId` параметра.</span><span class="sxs-lookup"><span data-stu-id="11489-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="11489-129">Имя</span><span class="sxs-lookup"><span data-stu-id="11489-129">Name</span></span>|<span data-ttu-id="11489-130">Значение</span><span class="sxs-lookup"><span data-stu-id="11489-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="11489-131">None</span><span class="sxs-lookup"><span data-stu-id="11489-131">None</span></span>|<span data-ttu-id="11489-132">0</span><span class="sxs-lookup"><span data-stu-id="11489-132">0</span></span>|  
|<span data-ttu-id="11489-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="11489-133">SHA-1</span></span>|<span data-ttu-id="11489-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="11489-134">0x8004</span></span>|  
|<span data-ttu-id="11489-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="11489-135">SHA-256</span></span>|<span data-ttu-id="11489-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="11489-136">0x800c</span></span>|  
|<span data-ttu-id="11489-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="11489-137">SHA-384</span></span>|<span data-ttu-id="11489-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="11489-138">0x800d</span></span>|  
|<span data-ttu-id="11489-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="11489-139">SHA-512</span></span>|<span data-ttu-id="11489-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="11489-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="11489-141">Требования</span><span class="sxs-lookup"><span data-stu-id="11489-141">Requirements</span></span>  

 <span data-ttu-id="11489-142">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11489-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11489-143">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="11489-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="11489-144">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11489-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11489-145">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11489-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11489-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="11489-146">See also</span></span>

- [<span data-ttu-id="11489-147">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="11489-147">StrongNameTokenFromPublicKey Method</span></span>](iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="11489-148">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="11489-148">PublicKeyBlob Structure</span></span>](../strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="11489-149">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="11489-149">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
- [<span data-ttu-id="11489-150">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="11489-150">StrongNameGetPublicKey Method</span></span>](iclrstrongname-strongnamegetpublickey-method.md)
