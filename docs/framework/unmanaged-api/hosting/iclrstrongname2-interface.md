---
title: Интерфейс ICLRStrongName2
ms.date: 03/30/2017
api_name:
- ICLRStrongName2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName2
helpviewer_keywords:
- ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type:
- apiref
ms.openlocfilehash: 9715369f4cf1b2a7078be14a2fc597f735ab6fd3
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763167"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="4a9b1-102">Интерфейс ICLRStrongName2</span><span class="sxs-lookup"><span data-stu-id="4a9b1-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="4a9b1-103">Предоставляет возможность создания строгих имен с помощью группы SHA-2 алгоритмов безопасных хэширования (SHA-256, SHA-384 и SHA-512).</span><span class="sxs-lookup"><span data-stu-id="4a9b1-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4a9b1-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4a9b1-104">Methods</span></span>  
  
|<span data-ttu-id="4a9b1-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4a9b1-105">Method</span></span>|<span data-ttu-id="4a9b1-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4a9b1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4a9b1-107">Метод StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="4a9b1-107">StrongNameGetPublicKeyEx Method</span></span>](strongnamegetpublickeyex-method.md)|<span data-ttu-id="4a9b1-108">Получает открытый ключ из пары открытого и закрытого ключей и задает алгоритм хеширования и алгоритм подписи.</span><span class="sxs-lookup"><span data-stu-id="4a9b1-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="4a9b1-109">Метод StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="4a9b1-109">StrongNameSignatureVerificationEx2 Method</span></span>](strongnamesignatureverificationex2-method.md)|<span data-ttu-id="4a9b1-110">Проверяет подпись сборки со строгим именем и обеспечивает сопоставление ключа ECMA с реальным ключом.</span><span class="sxs-lookup"><span data-stu-id="4a9b1-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a9b1-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="4a9b1-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a9b1-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4a9b1-112">Requirements</span></span>  
 <span data-ttu-id="4a9b1-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a9b1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a9b1-114">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="4a9b1-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4a9b1-115">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4a9b1-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a9b1-116">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a9b1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
