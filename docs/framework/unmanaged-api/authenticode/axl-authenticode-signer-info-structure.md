---
description: 'Дополнительные сведения: структура AXL_AUTHENTICODE_SIGNER_INFO'
title: Структура AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
ms.openlocfilehash: 940652cf184e26f141df806b060c391333d1bb95
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781965"
---
# <a name="axl_authenticode_signer_info-structure"></a>Структура AXL_AUTHENTICODE_SIGNER_INFO

Определяет информацию о подписавшем Authenticode.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`cbSize`|Размер этой структуры.|  
|`dwError`|Код ошибки.|  
|`algHash`|Хэш-алгоритм.|  
|`pwszHash`|Хэш-код.|  
|`pwszDescription`|Описание.|  
|`pwszDescriptionUrl`|URL-адрес описания.|  
|`pChainContext`|Контекст цепочки подписавшего. См. структуру [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .|  
  
## <a name="see-also"></a>См. также

- [Authenticode](index.md)
