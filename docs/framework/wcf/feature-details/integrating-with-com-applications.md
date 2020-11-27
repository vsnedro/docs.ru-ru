---
title: Интеграция с приложениями COM
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
ms.openlocfilehash: bc58e22b64284d66367302d55b5c9554c9ec0d72
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268239"
---
# <a name="integrating-with-com-applications"></a>Интеграция с приложениями COM

Службы Windows Communication Foundation (WCF) можно интегрировать непосредственно в существующий код с помощью моникера службы WCF. Моникер служб можно использовать в широком наборе сред разработки на базе модели COM, например в Office VBA, Visual Basic 6.0 и Visual C++ 6.0.  
  
## <a name="in-this-section"></a>в этом разделе  

 [Общие сведения об интеграции с приложениями COM](integrating-with-com-applications-overview.md)  
 Предоставляет общие сведения об основных компонентах процесса объединения.  
  
 [Практическое руководство. Регистрация и настройка моникера службы](how-to-register-and-configure-a-service-moniker.md)  
 Чтобы использовать моникер службы WCF в COM-приложении, зарегистрируйте необходимые типы с атрибутами в COM и настройте приложение COM и моникер с требуемой конфигурацией привязки.  
  
 [Практическое руководство. Использование моникера службы Windows Communication Foundation без регистрации](use-the-wcf-service-moniker-without-registration.md)  
 Содержит объяснения, как получить определение контракта в форме документа языка описания веб-служб (WSDL) или из конечной точки WS-MetadataExchange.  
  
 [Практическое руководство. Использование моникера службы с контрактами WSDL](how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 Описывает, как вызвать пример WCF с помощью моникера WSDL языка WCF.  
  
 [Практическое руководство. Использование моникера службы с контрактами обмена метаданными](how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 Описывает, как вызвать пример WCF с помощью моникера WCF, указывающего конечную точку обмена метаданными.  
  
 [Практическое руководство. Задание учетных данных безопасности канала](how-to-specify-channel-security-credentials.md)  
 Моникер службы WCF поддерживает `IChannelCredentials` интерфейс, который позволяет использовать ряд альтернативных методов для указания учетных данных канала.  
  
## <a name="reference"></a>Справочник  

 <xref:System.ServiceModel>  
  
## <a name="see-also"></a>См. также

- [Интеграция с приложениями COM+](integrating-with-com-plus-applications.md)
