---
title: Структура PublicKeyBlob
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
ms.openlocfilehash: 42cd3cc22fbbb8eb3d5ac44544fce36650b6461f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705934"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="e1e82-102">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="e1e82-102">PublicKeyBlob Structure</span></span>

<span data-ttu-id="e1e82-103">Представляет в двоичном формате открытый ключ пары открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="e1e82-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1e82-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1e82-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;
```  
  
## <a name="members"></a><span data-ttu-id="e1e82-105">Члены</span><span class="sxs-lookup"><span data-stu-id="e1e82-105">Members</span></span>  
  
|<span data-ttu-id="e1e82-106">Член</span><span class="sxs-lookup"><span data-stu-id="e1e82-106">Member</span></span>|<span data-ttu-id="e1e82-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e1e82-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="e1e82-108">Идентификатор для алгоритма подписи (типа `ALG_ID` , как определено в винкрипт. h) открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="e1e82-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="e1e82-109">Идентификатор для хэш-алгоритма (типа `ALG_ID` , как определено в винкрипт. h) открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="e1e82-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="e1e82-110">Длина ключа в байтах.</span><span class="sxs-lookup"><span data-stu-id="e1e82-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="e1e82-111">Массив байтов переменной длины, который содержит значение ключа в формате, возвращенном CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="e1e82-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1e82-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e1e82-112">Remarks</span></span>  

 <span data-ttu-id="e1e82-113">`PublicKeyBlob`Структура используется [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)и другими функциями строгого имени для представления открытого ключа пары открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="e1e82-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1e82-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e1e82-114">Requirements</span></span>  

 <span data-ttu-id="e1e82-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1e82-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1e82-116">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="e1e82-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e1e82-117">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e1e82-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e1e82-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1e82-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e82-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e1e82-119">See also</span></span>

- [<span data-ttu-id="e1e82-120">Функция StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="e1e82-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="e1e82-121">Функция StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="e1e82-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
