---
description: 'Дополнительные сведения о: интерфейс Иклрхостпротектионманажер'
title: Интерфейс ICLRHostProtectionManager
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
ms.openlocfilehash: 60d27a8c1a24720bbfdcde52a5495425279d5ac4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689252"
---
# <a name="iclrhostprotectionmanager-interface"></a>Интерфейс ICLRHostProtectionManager

Позволяет узлу блокировать выполнение конкретных управляемых классов, методов, свойств и полей в частично доверяемом коде.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[SetEagerSerializeGrantSets](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|Гарантирует, что некоторые редкие состояния гонки, которые могут вызвать неустранимые ошибки среды CLR, никогда не будут возникать.|  
|[Метод SetProtectedCategories](iclrhostprotectionmanager-setprotectedcategories-method.md)|Указывает категории управляемых типов и членов, выполнение которых должно быть заблокировано в частично доверенном коде.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление EApiCategories](eapicategories-enumeration.md)
- [Интерфейс ICLRControl](iclrcontrol-interface.md)
