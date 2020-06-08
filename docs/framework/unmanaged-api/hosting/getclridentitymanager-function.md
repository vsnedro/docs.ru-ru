---
title: Функция GetCLRIdentityManager
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
ms.openlocfilehash: 8b1e918edf641d38dd6b91d790bcaff8020293a0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493270"
---
# <a name="getclridentitymanager-function"></a>Функция GetCLRIdentityManager
Возвращает указатель на интерфейс, который позволяет среде CLR управлять удостоверениями.  
  
 Эта функция является устаревшей в .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `riid`  
 окне Объект `REFIID` (идентификатор интерфейса), указывающий, какой интерфейс следует получить. Это значение должно быть либо IID_ICLRAssemblyIdentityManager, либо IID_ICLRHostBindingPolicyManager.  
  
 `ppManager`  
 заполняет Указатель на адрес объекта [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) или [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) .  
  
## <a name="remarks"></a>Примечания  
 Вызовите функцию [жетреалпрокаддресс](getrealprocaddress-function.md) , чтобы получить указатель на `GetCLRIdentityManager` функцию.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorWks. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)
