---
title: Практическое руководство. Как настраивать протокол SSL в службе WCF, размещенной в IIS
description: Узнайте, как настроить службу WCF, размещенную в IIS, для использования безопасности транспорта HTTP, для которой требуется сертификат, зарегистрированный в службах IIS.
ms.date: 03/30/2017
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
ms.openlocfilehash: 8dc4692863d93e407a122c0ba93ae38323b8b213
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245262"
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a>Практическое руководство. Как настраивать протокол SSL в службе WCF, размещенной в IIS
В этом разделе описано, как настроить размещенную в IIS службу WCF для использования безопасности транспорта HTTP. Для безопасности транспорта HTTP требуется, чтобы SSL-сертификат был зарегистрирован в службах IIS. Если SSL-сертификат не установлен, для создания тестового сертификата можно использовать службы IIS. Затем необходимо добавить SSL-привязку для проекта веб-сайта и установить свойства проверки подлинности веб-сайта. Наконец, необходимо настроить службу WCF на использование протокола HTTPS.  
  
### <a name="creating-a-self-signed-certificate"></a>Создание самозаверяющего сертификата  
  
1. Откройте диспетчер служб IIS (inetmgr.exe) и выберите имя компьютера в левой части представления в виде дерева. В правой части экрана выберите сертификаты сервера  
  
     ![Начальный экран диспетчера IIS](media/mg-inetmgrhome.jpg "mg_INetMgrHome")  
  
2. В окне сертификаты сервера щелкните **создать самозаверяющий сертификат...** . Связь.  
  
     ![Создание&#45;самозаверяющего сертификата, подписанного с помощью служб IIS](media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")  
  
3. Введите понятное имя самозаверяющего сертификата и нажмите кнопку **ОК**.  
  
     ![Диалоговое окно создания самозаверяющего сертификата&#45;](media/mg-mycert.jpg "mg_MyCert")  
  
     В окне **Сертификаты сервера** теперь отображаются только что созданные самозаверяющие сертификаты.  
  
     ![Окно "Сертификат сервера"](media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")  
  
     Созданный сертификат устанавливается в хранилище доверенных корневых центров сертификации.  
  
### <a name="add-ssl-binding"></a>Добавление привязки SSL  
  
1. По-прежнему в службы IIS Manager разверните папку **сайты** , а затем папку **веб-сайт по умолчанию** в древовидном представлении в левой части экрана.  
  
2. Щелкните **привязки....** Ссылка в разделе **действия** в верхней правой части окна.  
  
     ![Добавление привязки SSL](media/mg-addsslbinding.jpg "mg_AddSSLBinding")  
  
3. В окне "привязки сайта" нажмите кнопку **Добавить** .  
  
     ![Диалоговое окно "Привязки сайта"](media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")  
  
4. В диалоговом окне **Добавление привязки сайта** выберите HTTPS для типа и понятное имя самозаверяющего сертификата, который вы только что создали.  
  
     ![Пример привязки сайта](media/mg-mycertbinding.jpg "mg_MyCertBinding")  
  
### <a name="configure-virtual-directory-for-ssl"></a>Настройка виртуального каталога для SSL  
  
1. В диспетчере служб IIS выберите виртуальный каталог, содержащий безопасную службу WCF.  
  
2. В центральной области окна выберите **Параметры SSL** в разделе IIS.  
  
     ![Параметры SSL для виртуального каталога](media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")  
  
3. В области Параметры SSL установите флажок **требовать SSL** и щелкните ссылку **Применить** в разделе **действия** в правой части экрана.  
  
     ![Параметры SSL виртуального каталога](media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")  
  
### <a name="configure-wcf-service-for-http-transport-security"></a>Настройка службы WCF для безопасности транспорта HTTP  
  
1. В файле web.config службы WCF настройте привязку HTTP на использование безопасности транспорта, как показано в следующем фрагменте XML.  
  
    ```xml  
    <bindings>  
          <basicHttpBinding>  
            <binding name="secureHttpBinding">  
              <security mode="Transport">  
                <transport clientCredentialType="None"/>  
              </security>  
            </binding>  
          </basicHttpBinding>  
    </bindings>  
    ```  
  
2. Укажите службу и конечную точку службы, как показано в следующем фрагменте XML.  
  
    ```xml  
    <services>  
          <service name="MySecureWCFService.Service1">  
            <endpoint address=""  
                      binding="basicHttpBinding"  
                      bindingConfiguration="secureHttpBinding"  
                      contract="MySecureWCFService.IService1"/>  
  
            <endpoint address="mex"  
                      binding="mexHttpsBinding"  
                      contract="IMetadataExchange" />  
          </service>  
    </services>  
    ```  
  
## <a name="example"></a>Пример  
 Ниже приведен полный пример файла web.config для службы WCF, использующей безопасность транспорта HTTP  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <services>  
      <service name="MySecureWCFService.Service1">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="secureHttpBinding"  
                  contract="MySecureWCFService.IService1"/>  
  
        <endpoint address="mex"  
                  binding="mexHttpsBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="secureHttpBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <!-- To avoid disclosing metadata information, set the value below to false and remove the metadata endpoint above before deployment -->  
          <serviceMetadata httpsGetEnabled="true"/>  
          <!-- To receive exception details in faults for debugging purposes, set the value below to true.  Set to false before deployment to avoid disclosing exception information -->  
          <serviceDebug includeExceptionDetailInFaults="false"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
  </system.serviceModel>  
  <system.webServer>  
    <modules runAllManagedModulesForAllRequests="true"/>  
  </system.webServer>  
  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Размещение в службах IIS](hosting-in-internet-information-services.md)
- [Инструкции по размещению в службах IIS](../samples/internet-information-service-hosting-instructions.md)
- [Рекомендации по размещению в службах IIS](internet-information-services-hosting-best-practices.md)
- [Размещение в службах IIS с использованием встроенного кода](../samples/iis-hosting-using-inline-code.md)
