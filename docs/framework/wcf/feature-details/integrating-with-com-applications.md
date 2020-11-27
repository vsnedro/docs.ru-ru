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
# <a name="integrating-with-com-applications"></a><span data-ttu-id="16e36-102">Интеграция с приложениями COM</span><span class="sxs-lookup"><span data-stu-id="16e36-102">Integrating with COM Applications</span></span>

<span data-ttu-id="16e36-103">Службы Windows Communication Foundation (WCF) можно интегрировать непосредственно в существующий код с помощью моникера службы WCF.</span><span class="sxs-lookup"><span data-stu-id="16e36-103">Windows Communication Foundation (WCF) services can be integrated directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="16e36-104">Моникер служб можно использовать в широком наборе сред разработки на базе модели COM, например в Office VBA, Visual Basic 6.0 и Visual C++ 6.0.</span><span class="sxs-lookup"><span data-stu-id="16e36-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16e36-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="16e36-105">In This Section</span></span>  

 [<span data-ttu-id="16e36-106">Общие сведения об интеграции с приложениями COM</span><span class="sxs-lookup"><span data-stu-id="16e36-106">Integrating with COM Applications Overview</span></span>](integrating-with-com-applications-overview.md)  
 <span data-ttu-id="16e36-107">Предоставляет общие сведения об основных компонентах процесса объединения.</span><span class="sxs-lookup"><span data-stu-id="16e36-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="16e36-108">Практическое руководство. Регистрация и настройка моникера службы</span><span class="sxs-lookup"><span data-stu-id="16e36-108">How to: Register and Configure a Service Moniker</span></span>](how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="16e36-109">Чтобы использовать моникер службы WCF в COM-приложении, зарегистрируйте необходимые типы с атрибутами в COM и настройте приложение COM и моникер с требуемой конфигурацией привязки.</span><span class="sxs-lookup"><span data-stu-id="16e36-109">To use the WCF service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="16e36-110">Практическое руководство. Использование моникера службы Windows Communication Foundation без регистрации</span><span class="sxs-lookup"><span data-stu-id="16e36-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="16e36-111">Содержит объяснения, как получить определение контракта в форме документа языка описания веб-служб (WSDL) или из конечной точки WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="16e36-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="16e36-112">Практическое руководство. Использование моникера службы с контрактами WSDL</span><span class="sxs-lookup"><span data-stu-id="16e36-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="16e36-113">Описывает, как вызвать пример WCF с помощью моникера WSDL языка WCF.</span><span class="sxs-lookup"><span data-stu-id="16e36-113">Describes how to call a WCF sample using a WCF WSDL moniker.</span></span>  
  
 [<span data-ttu-id="16e36-114">Практическое руководство. Использование моникера службы с контрактами обмена метаданными</span><span class="sxs-lookup"><span data-stu-id="16e36-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="16e36-115">Описывает, как вызвать пример WCF с помощью моникера WCF, указывающего конечную точку обмена метаданными.</span><span class="sxs-lookup"><span data-stu-id="16e36-115">Describes how to call a WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="16e36-116">Практическое руководство. Задание учетных данных безопасности канала</span><span class="sxs-lookup"><span data-stu-id="16e36-116">How to: Specify Channel Security Credentials</span></span>](how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="16e36-117">Моникер службы WCF поддерживает `IChannelCredentials` интерфейс, который позволяет использовать ряд альтернативных методов для указания учетных данных канала.</span><span class="sxs-lookup"><span data-stu-id="16e36-117">The WCF service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="16e36-118">Справочник</span><span class="sxs-lookup"><span data-stu-id="16e36-118">Reference</span></span>  

 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="16e36-119">См. также</span><span class="sxs-lookup"><span data-stu-id="16e36-119">See also</span></span>

- [<span data-ttu-id="16e36-120">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="16e36-120">Integrating with COM+ Applications</span></span>](integrating-with-com-plus-applications.md)
