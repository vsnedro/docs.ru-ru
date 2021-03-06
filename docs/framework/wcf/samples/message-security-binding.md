---
title: Привязка безопасности сообщений
ms.date: 03/30/2017
ms.assetid: a4570ce7-864e-461b-85d8-0f7bcc53c2c8
ms.openlocfilehash: a4d13eabc0d086a9cfe58c95165b0405f60fcf14
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294382"
---
# <a name="message-security-binding"></a>Привязка безопасности сообщений

Этот раздел содержит примеры, демонстрирующие привязку безопасности сообщений в службах Windows в WCF.  
  
## <a name="in-this-section"></a>в этом разделе  

 [Безопасность сообщений с возможностью анонимного доступа](message-security-anonymous.md)  
 В этом примере демонстрируется реализация приложения Windows Communication Foundation (WCF), использующего безопасность на уровне сообщений без проверки подлинности клиента, но требующего проверки подлинности сервера с помощью сертификата X. 509 на сервере.  
  
 [Сертификат безопасности сообщений](message-security-certificate.md)  
 В этом образце показано, как реализовать приложение, использующее протокол WS-Security и проверку подлинности с использованием сертификата X.509 v3 для клиента и требующее проверки подлинности сервера с использованием сертификата X.509 v3 сервера.  
  
 [Безопасность сообщений с использованием имени пользователя](message-security-user-name.md)  
 В этом образце показано, как реализовать приложение, использующее протокол WS-Security и проверку подлинности имен пользователя для клиента и требующее проверки подлинности сервера с использованием сертификата X.509v3 сервера.  
  
 [Безопасность сообщений с использованием механизмов Windows](message-security-windows.md)  
 В этом образце показывается, как настраивать привязку <xref:System.ServiceModel.WSHttpBinding> для использования безопасности на уровне сообщений с проверкой подлинности Windows.
