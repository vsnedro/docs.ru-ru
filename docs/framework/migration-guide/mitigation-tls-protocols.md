---
title: Устранение рисков. Протоколы TLS
description: Узнайте о последствии и устранении рисков в связи с изменениями протокола TLS, начиная с .NET Framework 4.6.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
ms.openlocfilehash: bb5aab3361663d7b5401d7e68688265fbc65b36f
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475363"
---
# <a name="mitigation-tls-protocols"></a>Устранение рисков. Протоколы TLS
Начиная с версии .NET Framework 4.6, классы <xref:System.Net.ServicePointManager?displayProperty=nameWithType> и <xref:System.Net.Security.SslStream?displayProperty=nameWithType> могут использовать один из трех следующих протоколов: Tls1.0, Tls1.1 или Tls 1.2. Протокол SSL 3.0 и шифрование RC4 не поддерживаются.  
  
## <a name="impact"></a>Последствия  
 Это изменение влияет:  
  
- на все приложения, использующие протокол SSL для связи с сервером HTTPS или сервером сокетов с помощью любого из следующих типов: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> и <xref:System.Net.Security.SslStream>;  
  
- на все приложения на стороне сервера, которые нельзя обновить для поддержки Tls1.0, Tls1.1 или Tls 1.2.  
  
## <a name="mitigation"></a>Устранение рисков  
 Рекомендуется обновить приложения на стороне сервера для использования Tls1.0, Tls1.1 или Tls 1.2. Если это невозможно, или если клиентские приложения не работают, можно использовать класс <xref:System.AppContext>, чтобы отказаться от этой функции одним из двух способов.  
  
- Программно с помощью фрагмента кода следующего вида:  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     Поскольку объект <xref:System.Net.ServicePointManager> инициализируется только один раз, определение этих параметров совместимости должно быть первым действием приложения.  
  
- путем добавления следующей строки в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла app.config:  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 Следует, тем не менее, заметить, что отказ от поведения по умолчанию не рекомендуется, поскольку приводит к снижению безопасности приложения.  
  
## <a name="see-also"></a>См. также

- [Совместимость приложений](application-compatibility.md)
