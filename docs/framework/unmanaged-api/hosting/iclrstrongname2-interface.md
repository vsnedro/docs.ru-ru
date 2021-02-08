---
description: 'Дополнительные сведения о: интерфейс ICLRStrongName2'
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
ms.openlocfilehash: 7442bd054af735e9f1b75b05feb8724dfa993f73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781796"
---
# <a name="iclrstrongname2-interface"></a>Интерфейс ICLRStrongName2

Предоставляет возможность создания строгих имен с помощью группы SHA-2 алгоритмов безопасных хэширования (SHA-256, SHA-384 и SHA-512).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод StrongNameGetPublicKeyEx](strongnamegetpublickeyex-method.md)|Получает открытый ключ из пары открытого и закрытого ключей и задает алгоритм хеширования и алгоритм подписи.|  
|[Метод StrongNameSignatureVerificationEx2](strongnamesignatureverificationex2-method.md)|Проверяет подпись сборки со строгим именем и обеспечивает сопоставление ключа ECMA с реальным ключом.|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
