---
description: 'Дополнительные сведения о: интерфейс ICLRAssemblyReferenceList'
title: Интерфейс ICLRAssemblyReferenceList
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
ms.openlocfilehash: f5ef4efd343ebc18c443482f4697a3d299c5aac1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716827"
---
# <a name="iclrassemblyreferencelist-interface"></a>Интерфейс ICLRAssemblyReferenceList

Управляет списком сборок, загружаемых средой CLR, а не узлом.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод IsAssemblyReferenceInList](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|Возвращает значение, указывающее, ссылается ли указанный указатель на сборку в списке.|  
|[Метод IsStringAssemblyReferenceInList](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|Возвращает значение, указывающее, совпадает ли заданное имя с именем сборки в списке.|  
  
## <a name="remarks"></a>Remarks  

 Вызовите метод [ICLRAssemblyIdentityManager:: getclrassemblyreferencelist-](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) , чтобы получить указатель на экземпляр `ICLRAssemblyReferenceList` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
- [Интерфейс IHostAssemblyStore](ihostassemblystore-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
