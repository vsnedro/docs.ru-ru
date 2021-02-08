---
description: 'Дополнительные сведения о методе: ICLRAssemblyIdentityManager:: Жетреференцедассемблиесфромфиле'
title: Метод ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferenceAssembliesFromFile method [.NET Framework hosting]
- GetReferenceAssembliesFromFile method [.NET Framework hosting]
ms.assetid: eed63d31-d977-4c7d-9443-f9d37a2a7d81
topic_type:
- apiref
ms.openlocfilehash: 46b2f392746c6e23e2a8a11aded5eacd8f5a597b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790063"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a>Метод ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile

Возвращает экземпляр [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) , содержащий список сборок, на которые ссылается сборка по указанному пути к файлу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pwzFilePath`  
 окне Путь к сборке, которую необходимо вычислить.  
  
 `dwFlags`  
 окне Предоставляется для будущего расширения. CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT является единственным значением, которое поддерживает Текущая версия среды CLR.  
  
 `pExcludeAssembliesList`  
 окне Указатель на объект [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) , представляющий сборки, которые должны быть исключены из `ppReferenceEnum` .  
  
 `ppReferenceEnum`  
 заполняет Указатель на адрес `ICLRReferenceAssemblyEnum` объекта, который содержит данные идентификации сборки для сборок, на которые ссылается сборка `pwzFilePath` , за исключением сборок, представленных в `pExcludeAssembliesList` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод возвратился успешно.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  

 Вызывающий объект может исключить набор известных ссылок на сборки из возвращенного списка. Этот набор определяется `pExcludeAssembliesList` параметром.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
- [Интерфейс ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Интерфейс ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md)
