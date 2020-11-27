---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: d3625865484568746888ef0638d9a8501e610bef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273208"
---
# <a name="serviceauthorizationbehavior"></a>ServiceAuthorizationBehavior

ServiceAuthorizationBehavior  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс ServiceAuthorizationBehavior не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс ServiceAuthorizationBehavior имеет следующие свойства.  
  
### <a name="impersonatecallerforalloperations"></a>ImpersonateCallerForAllOperations  

 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, которое определяет, будет ли служба пытаться производить олицетворение при помощи учетных данных, содержащихся во входящем сообщении.  
  
### <a name="principalpermissionmode"></a>PrincipalPermissionMode  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Участник, используемый для выполнения операций на сервере.  
  
### <a name="roleprovider"></a>RoleProvider  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Имя поставщика ролей ASP.NET.  
  
### <a name="serviceauthorizationmanager"></a>ServiceAuthorizationManager  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Диспетчер авторизации, используемый для пользовательской авторизации.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
