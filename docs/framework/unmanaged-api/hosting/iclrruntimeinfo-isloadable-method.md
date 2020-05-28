---
title: Метод ICLRRuntimeInfo::IsLoadable
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
ms.openlocfilehash: a1cd169fc4be5b1dd3ab1a83f4ad143ba2e2442b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007368"
---
# <a name="iclrruntimeinfoisloadable-method"></a>Метод ICLRRuntimeInfo::IsLoadable
Указывает, можно ли загрузить среду выполнения, связанную с этим интерфейсом, в текущий процесс, принимая во внимание другие среды выполнения, которые уже могут быть загружены в процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbLoadable`  
 [out] `true` значение, если эту среду выполнения можно загрузить в текущий процесс; в противном случае — `false` .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `pbLoadable` имеет значение NULL.|  
  
## <a name="remarks"></a>Примечания  
 Если в процесс уже загружена другая среда выполнения, и среда выполнения, связанная с этим интерфейсом, может быть загружена для внутрипроцессного параллельного выполнения, `pbLoadable` возвращает `true` . Если две среды выполнения не могут выполняться параллельно, `pbLoadable` возвращает `false` . Например, общеязыковая среда выполнения (CLR) версии 4 может работать параллельно в том же процессе с CLR версии 2,0 или CLR версии 1,1. Однако среда CLR версии 1,1 и CLR версии 2,0 не могут выполняться параллельно в процессе.  
  
 Если в процесс не загружены среды выполнения, этот метод всегда возвращает значение `true` .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)
