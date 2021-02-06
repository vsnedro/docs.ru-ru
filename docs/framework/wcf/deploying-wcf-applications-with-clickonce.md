---
description: Дополнительные сведения см. в статье Развертывание приложений WCF с помощью ClickOnce.
title: Развертывание приложений WCF с помощью ClickOnce
ms.date: 03/30/2017
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
ms.openlocfilehash: f0a78bab6bbe7ddfd431e8e12bfe1ca9c9143143
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646092"
---
# <a name="deploying-wcf-applications-with-clickonce"></a>Развертывание приложений WCF с помощью ClickOnce

Клиентские приложения, использующие Windows Communication Foundation (WCF), могут быть развернуты с помощью технологии ClickOnce. Эта технология позволяет им использовать преимущества средств защиты среды выполнения, предоставляемых управлением доступом для кода, если приложения снабжены цифровой подписью с надежным сертификатом. Сертификат, используемый для подписывания приложения ClickOnce, должен располагаться в хранилище надежных издателей, а локальная политика безопасности на клиентском компьютере должна быть настроена таким образом, чтобы предоставлять разрешения полного доверия приложениям, подписанным с использованием сертификата издателя.  
  
 Сведения о настройке приложений ClickOnce и доверенных издателей см. в разделе [Настройка доверенных издателей ClickOnce](/previous-versions/dotnet/articles/ms996418(v=msdn.10)).  
  
## <a name="see-also"></a>См. также

- [Общие сведения о развертывании доверенных приложений](/visualstudio/deployment/trusted-application-deployment-overview)
- [Развертывание ClickOnce для приложений Windows Forms](/previous-versions/visualstudio/visual-studio-2008/wh45kb66(v=vs.90))
