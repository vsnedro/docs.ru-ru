---
title: Интерфейс ICLRMetaHostPolicy
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
ms.openlocfilehash: 515b73b019c683bd3e5aa3b895ee5623e75e4ad0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707611"
---
# <a name="iclrmetahostpolicy-interface"></a>Интерфейс ICLRMetaHostPolicy

Предоставляет метод [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) , возвращающий указатель на интерфейс среды CLR на основе критериев политики, управляемой сборки, версии и файла конфигурации.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md)|Предоставляет предпочтительный интерфейс CLR на основе критериев политики, управляемой сборки, версии и файла конфигурации.|  
  
## <a name="remarks"></a>Комментарии  

 Ссылку на этот интерфейс можно получить, вызвав функцию [клркреатеинстанце](clrcreateinstance-function.md) , как показано в следующем коде:  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> Этот интерфейс фактически не загружает и не активирует среду CLR, а просто возвращает предпочтительную версию среды CLR на основе установленных или загруженных версий.  
  
 В .NET Framework 4 API размещения консолидируются политики, чтобы узлы с конкретными потребностями могли использовать базовые функции без непреднамеренной потерь. Например, многие из MSCorEE.dll экспортов будут привязаны к определенной среде CLR, хотя метод может не потребовать его логически. Перечисление [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) предоставляет политики привязки, общие для большинства узлов.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)
