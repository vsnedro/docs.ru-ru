---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.date: 03/30/2017
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
ms.openlocfilehash: cb7019f1e4b47bde7c98b0109afa7b0125b7ef63
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84577309"
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a>System.ServiceModel.Channels.PeerNodeAuthenticationFailure
Подтверждение безопасности с потенциальным соседним узлом завершилось неуспешно.  
  
## <a name="description"></a>Описание  
 Эта трассировка возникает при попытке установить безопасное соединение с соседним узлом. Это может произойти из-за недостаточных или неправильных учетных данных.  
  
 PeerChannel распознает один тип маркеров для строгой идентификации (сертификаты X.509), что обеспечивает строгую модель удостоверения, зависящую от типа проверки подлинности и авторизации, который может быть реализован. PeerChannel также обеспечивает поддержку простых приложений посредством использования паролей. Пароли могут использоваться только для разрешения входа в сеанс; их нельзя использовать для проверки подлинности сообщений. Это связано с тем, что симметричный маркер, общий для участников одноранговой группы, сложно (и не следует) использовать для проверки подлинности источника.  
  
## <a name="troubleshooting"></a>Диагностика  
 Обеспечьте, чтобы все соседние узлы имели соответствующие учетные данные безопасности.  
  
## <a name="see-also"></a>Дополнительно

- [Безопасность одноранговых каналов](../../feature-details/peer-channel-security.md)
- [Трассировка](index.md)
- [Использование трассировки для устранения неполадок приложения](using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../index.md)
