---
description: 'Дополнительные сведения: System. ServiceModel. Channels. Пирнодеаусентикатионфаилуре'
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.date: 03/30/2017
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
ms.openlocfilehash: 751202abd3e199a03fc4ee0bf1252d4a8027e0cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99634938"
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a>System.ServiceModel.Channels.PeerNodeAuthenticationFailure

Подтверждение безопасности с потенциальным соседним узлом завершилось неуспешно.  
  
## <a name="description"></a>Описание  

 Эта трассировка возникает при попытке установить безопасное соединение с соседним узлом. Это может произойти из-за недостаточных или неправильных учетных данных.  
  
 PeerChannel распознает один тип маркеров для строгой идентификации (сертификаты X.509), что обеспечивает строгую модель удостоверения, зависящую от типа проверки подлинности и авторизации, который может быть реализован. PeerChannel также обеспечивает поддержку простых приложений посредством использования паролей. Пароли могут использоваться только для разрешения входа в сеанс; их нельзя использовать для проверки подлинности сообщений. Это связано с тем, что симметричный маркер, общий для участников одноранговой группы, сложно (и не следует) использовать для проверки подлинности источника.  
  
## <a name="troubleshooting"></a>Устранение неполадок  

 Обеспечьте, чтобы все соседние узлы имели соответствующие учетные данные безопасности.  
  
## <a name="see-also"></a>См. также

- [Безопасность одноранговых каналов](../../feature-details/peer-channel-security.md)
- [Трассировка](index.md)
- [Использование трассировки для устранения неполадок приложения](using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../index.md)
