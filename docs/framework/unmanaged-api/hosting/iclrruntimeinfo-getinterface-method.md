---
description: 'Дополнительные сведения о методе ICLRRuntimeInfo:: interface'
title: Метод ICLRRuntimeInfo::GetInterface
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type:
- apiref
ms.openlocfilehash: 5a5c55823ff9954735a712423d8aaab1256c947d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637135"
---
# <a name="iclrruntimeinfogetinterface-method"></a>Метод ICLRRuntimeInfo::GetInterface

Загружает среду CLR в текущий процесс и возвращает указатели на интерфейсы среды выполнения, такие как [ICLRRuntimeHost](iclrruntimehost-interface.md), [метод iclrstrongname](iclrstrongname-interface.md)и [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).  
  
 Этот метод заменяет все `CorBindTo` функции * в разделе [устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a>Параметры  

 `rclsid`  
 окне Интерфейс CLSID для компонентного класса.  
  
 `riid`  
 окне IID запрашиваемого `rclsid` интерфейса.  
  
 `ppUnk`  
 заполняет Указатель на запрашиваемый интерфейс.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `ppUnk` имеет значение null.|  
|E_OUTOFMEMORY|Недостаточно памяти для выполнения запроса.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Другая среда выполнения уже привязана к устаревшей политике активации CLR версии 2.|  
  
## <a name="remarks"></a>Remarks  

 Этот метод приводит к тому, что среда CLR загружается, но не инициализируется.  
  
 В следующей таблице приведены поддерживаемые сочетания для `rclsid` и `riid` .  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|CLSID_CorMetaDataDispenser|IID_IMetaDataDispenser, IID_IMetaDataDispenserEx|  
|CLSID_CorMetaDataDispenserRuntime|IID_IMetaDataDispenser, IID_IMetaDataDispenserEx|  
|CLSID_CorRuntimeHost|IID_ICorRuntimeHost|  
|CLSID_CLRRuntimeHost|IID_ICLRRuntimeHost|  
|CLSID_TypeNameFactory|IID_ITypeNameFactory|  
|CLSID_CLRDebuggingLegacy|IID_ICorDebug|  
|||  
|CLSID_CLRStrongName|IID_ICLRStrongName|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)
