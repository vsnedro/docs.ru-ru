---
description: 'Дополнительные сведения о: интерфейс ICLRProbingAssemblyEnum'
title: Интерфейс ICLRProbingAssemblyEnum
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
ms.openlocfilehash: 1fd11e237f02bab85ec2b41df49d7d8a2f27e1e1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716516"
---
# <a name="iclrprobingassemblyenum-interface"></a>Интерфейс ICLRProbingAssemblyEnum

Предоставляет методы, позволяющие узлу получить идентификаторы проверки сборки с помощью сведений об удостоверении сборки, которые являются внутренними для среды CLR, без необходимости создавать или понимать это удостоверение.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Get](iclrprobingassemblyenum-get-method.md)|Возвращает удостоверение сборки по указанному индексу.|  
  
## <a name="remarks"></a>Remarks  

 Методы, такие как [ICLRAssemblyIdentityManager:: жетпробингассемблиесфромреференце](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) , возвращают `ICLRProbingAssemblyEnum` экземпляр.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
- [Интерфейс ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
