---
title: Практическое руководство. Создание пользовательской привязки надежного сеанса с использованием HTTPS
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: 70f8f4f33626ab0d1705e03750bfd9baa324e60a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599000"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a>Практическое руководство. Создание пользовательской привязки надежного сеанса с использованием HTTPS

В этом разделе рассматривается использование механизма обеспечения безопасности транспорта через протокол SSL и надежные сеансы. Для использования надежных сеансов через протокол HTTPS требуется создать пользовательскую привязку, использующую надежный сеанс и транспорт HTTPS. Надежный сеанс можно включить принудительно с помощью кода или декларативно в файле конфигурации. В этой процедуре используются файлы конфигурации клиента и службы для включения надежного сеанса и [**\<httpsTransport>**](../../configure-apps/file-schema/wcf/httpstransport.md) элемента.

Основная часть этой процедуры заключается в том, что **\<endpoint>** элемент Configuration содержит `bindingConfiguration` атрибут, который ссылается на конфигурацию пользовательской привязки с именем `reliableSessionOverHttps` . [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md)Элемент Configuration ссылается на это имя, чтобы указать, что надежный сеанс и транспорт HTTPS используются, включая **\<reliableSession>** элементы и **\<httpsTransport>** .

Исходный экземпляр этого примера см. в разделе [Пользовательская привязка надежного сеанса по протоколу HTTPS](../samples/custom-binding-reliable-session-over-https.md).

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Настройка службы с помощью CustomBinding для использования надежного сеанса с HTTPS

1. Определите контракт службы для данного типа службы.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. Реализуйте контракт службы в классе службы. Обратите внимание, что адрес или сведения о привязке не указываются внутри реализации службы. Вам не нужно писать код для получения адреса или сведений о привязке из файла конфигурации.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. Создайте файл *Web. config* , чтобы настроить конечную точку для `CalculatorService` с пользовательской привязкой с именем `reliableSessionOverHttps` , использующей надежный сеанс и транспорт HTTPS.

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. Создайте файл *Service. svc* , содержащий строку:

   `<%@ServiceHost language=c# Service="CalculatorService" %>`

1. Поместите файл *Service. svc* в виртуальный каталог службы IIS (IIS).

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Настройка клиента с помощью CustomBinding для использования надежного сеанса с HTTPS

1. Используйте [средство служебной программы метаданных ServiceModel (*Svcutil. exe*)](../servicemodel-metadata-utility-tool-svcutil-exe.md) из командной строки для создания кода из метаданных службы.

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Созданный клиент содержит `ICalculator` интерфейс, определяющий контракт службы, которому должна соответствовать реализация клиента.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. Созданное клиентское приложение также содержит реализацию `ClientCalculator`. Обратите внимание, что адрес и сведения о привязке не указаны в реализации службы. Вам не нужно писать код для получения адреса и сведений о привязке из файла конфигурации.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. Настройте пользовательскую привязку с именем `reliableSessionOverHttps` , чтобы использовать транспорт HTTPS и надежные сеансы.

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. Создайте экземпляр класса `ClientCalculator` в приложении и вызовите операции службы.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. Скомпилируйте и запустите клиент.  

## <a name="net-framework-security"></a>безопасность платформы .NET Framework

Так как сертификат, используемый в этом примере, является тестовым сертификатом, созданным с помощью *Makecert. exe*, при попытке доступа к HTTPS-адресу, например, в браузере появляется предупреждение системы безопасности `https://localhost/servicemodelsamples/service.svc` .

## <a name="see-also"></a>Дополнительно

- [Надежные сеансы](reliable-sessions.md)
