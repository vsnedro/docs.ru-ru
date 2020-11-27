---
title: Безопасность поведений
ms.date: 03/30/2017
ms.assetid: 19710ae3-f197-4d28-ba9d-52e465006819
ms.openlocfilehash: c06c615af773affe9b824c6a862afcbadfb16295
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258742"
---
# <a name="behavior-security"></a>Безопасность поведений

В этом разделе приведены образцы, демонстрирующие настройку безопасности для поведения служб.  
  
## <a name="in-this-section"></a>в этом разделе  

 [Поведение аудита службы](service-auditing-behavior.md)  
 Этот образец демонстрирует, как использовать <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> для включения аудита событий безопасности во время выполнения операций службы.  
  
 [Поставщик членства и ролей](membership-and-role-provider.md)  
 В этом примере показано, как служба может использовать поставщиков членства и ролей ASP.NET для проверки подлинности и авторизации клиентов.  
  
 [Авторизация доступа к операциям службы](authorizing-access-to-service-operations.md)  
 В этом примере показано, как использовать [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) атрибут, чтобы разрешить использование <xref:System.Security.Permissions.PrincipalPermissionAttribute> атрибута для авторизации доступа к операциям службы.  
  
 [Олицетворение клиента](impersonating-the-client.md)  
 В этом образце показано, как олицетворять приложение абонента в службе таким образом, чтобы служба могла получить доступ к ресурсам системы от лица абонента.
