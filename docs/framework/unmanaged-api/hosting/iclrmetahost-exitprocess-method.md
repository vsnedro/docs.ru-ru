---
description: 'Дополнительные сведения о методе: ICLRMetaHost:: ExitProcess'
title: Метод ICLRMetaHost::ExitProcess
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
ms.openlocfilehash: 3bc832538a5ad2b457de758fc35a632b09c02974
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689161"
---
# <a name="iclrmetahostexitprocess-method"></a>Метод ICLRMetaHost::ExitProcess

Пытается корректно завершить работу всех загруженных сред выполнения, а затем завершить процесс. Заменяет функцию [корекситпроцесс](corexitprocess-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a>Параметры  

 `iExitCode`  
 окне Код выхода для процесса.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод никогда не возвращает, поэтому возвращаемое значение не определено.  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRMetaHost](iclrmetahost-interface.md)
- [Размещение](index.md)
