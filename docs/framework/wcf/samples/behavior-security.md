---
description: 'Дополнительные сведения: безопасность поведения'
title: Безопасность поведений
ms.date: 03/30/2017
ms.assetid: 19710ae3-f197-4d28-ba9d-52e465006819
ms.openlocfilehash: ba245a2c9558d40f22b9126ee0cf1560ed700ce8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778715"
---
# <a name="behavior-security"></a>Безопасность поведений

В этом разделе приведены образцы, демонстрирующие настройку безопасности для поведения служб.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Поведение аудита службы](service-auditing-behavior.md)  
 Этот образец демонстрирует, как использовать <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> для включения аудита событий безопасности во время выполнения операций службы.  
  
 [Поставщик членства и ролей](membership-and-role-provider.md)  
 В этом примере показано, как служба может использовать поставщиков членства и ролей ASP.NET для проверки подлинности и авторизации клиентов.  
  
 [Авторизация доступа к операциям службы](authorizing-access-to-service-operations.md)  
 В этом примере показано, как использовать [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) атрибут, чтобы разрешить использование <xref:System.Security.Permissions.PrincipalPermissionAttribute> атрибута для авторизации доступа к операциям службы.  
  
 [Олицетворение клиента](impersonating-the-client.md)  
 В этом образце показано, как олицетворять приложение абонента в службе таким образом, чтобы служба могла получить доступ к ресурсам системы от лица абонента.
