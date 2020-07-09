---
title: Практическое руководство. Размещение службы WCF в IIS
description: Узнайте, как создать службу WCF, размещенную в службы IIS (IIS). Размещение в службах IIS возможно только при использовании транспорта HTTP.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: 2ba0ae7adedc3bf0e0ca0cb92b4205edc968a5d8
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052017"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a>Практическое руководство. Размещение службы WCF в IIS
В этом разделе описаны основные шаги, необходимые для создания службы Windows Communication Foundation (WCF), размещенной в службы IIS (IIS). Предполагается, что читатель знаком со службами IIS и может использовать средство управления IIS для создания приложений служб IIS и управления такими приложениями. Дополнительные сведения о службах IIS см. в разделе [службы IIS](https://www.iis.net/). Служба WCF, работающая в среде IIS, обладает всеми преимуществами функций IIS, таких как перезапуск процессов, выключение в режиме простоя, мониторинг работоспособности процессов и активация на основе сообщений. Для реализации этого варианта размещения требуется правильно настроить службу IIS, но не требуется включать в приложение код размещения. Размещение в службах IIS возможно только при использовании транспорта HTTP.  
  
 Дополнительные сведения о взаимодействии WCF и ASP.NET см. в разделе [WCF Services and ASP.NET](wcf-services-and-aspnet.md). Дополнительные сведения о настройке безопасности см. в разделе [Безопасность](security.md).  
  
 Исходный экземпляр этого примера см. в разделе [размещение IIS с помощью встроенного кода](../samples/iis-hosting-using-inline-code.md).  
  
### <a name="to-create-a-service-hosted-by-iis"></a>Создание службы, размещенной в IIS  
  
1. Убедитесь, что службы IIS установлены и выполняются на компьютере. Дополнительные сведения об установке и настройке IIS см. в разделе [Установка и Настройка служб iis 7,0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista) .  
  
2. Создайте новую папку для файлов приложения с именем "Иишостедкалксервице", убедитесь, что ASP.NET имеет доступ к содержимому папки, и используйте средство управления IIS для создания нового приложения IIS, физически расположенного в этом каталоге приложения. Создайте для каталога приложения псевдоним «IISHostedCalc».  
  
3. Создайте в каталоге приложения новый файл с именем «service.svc». Измените этот файл, добавив следующий @ServiceHost элемент.  
  
   ```aspx-csharp
   <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>
   ```  
  
4. В каталоге приложения создайте подкаталог App_Code.  
  
5. Создайте файл кода с именем Service.cs во вложенном каталоге App_Code.  
  
6. Добавьте следующие операторы using в начало файла Service.cs.  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7. Добавьте следующее объявление пространства имен после операторов using.  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8. Определите контракт службы в пределах объявления пространства имен, как показано в следующем коде.  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. Реализуйте контракт службы после определения контракта службы, как показано в следующем коде.  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. Создайте в каталоге приложения файл с именем Web.config и добавьте в него следующий код конфигурации. Во время выполнения инфраструктура WCF использует эти сведения для создания конечной точки, с которой клиентские приложения могут обмениваться данными.  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]
  
     В этом примере конечные точки явно задаются в файле конфигурации. Если в службу не добавлена ни одна конечная точка, то среда выполнения добавляет конечные точки по умолчанию. Дополнительные сведения о конечных точках по умолчанию, привязках и поведении см. в разделе [упрощенная конфигурация](../simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../samples/simplified-configuration-for-wcf-services.md).  
  
11. Чтобы проверить правильность размещения службы, откройте экземпляр окна Internet Explorer и перейдите по URL-адресу службы: `http://localhost/IISHostedCalc/Service.svc`.  
  
## <a name="example"></a>Пример  
 Далее представлен полный код службы калькулятора, размещаемой в IIS.  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)]
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)]
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a>См. также раздел

- [Размещение в службах IIS](hosting-in-internet-information-services.md)
- [Размещение служб](../hosting-services.md)
- [Службы WCF и ASP.NET](wcf-services-and-aspnet.md)
- [Безопасность](security.md)
- [Функции размещения Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
