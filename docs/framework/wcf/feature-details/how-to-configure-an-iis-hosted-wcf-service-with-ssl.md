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
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a><span data-ttu-id="cff15-103">Практическое руководство. Как настраивать протокол SSL в службе WCF, размещенной в IIS</span><span class="sxs-lookup"><span data-stu-id="cff15-103">How to: Configure an IIS-hosted WCF service with SSL</span></span>
<span data-ttu-id="cff15-104">В этом разделе описано, как настроить размещенную в IIS службу WCF для использования безопасности транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="cff15-104">This topic describes how to set up an IIS-hosted WCF service to use HTTP transport security.</span></span> <span data-ttu-id="cff15-105">Для безопасности транспорта HTTP требуется, чтобы SSL-сертификат был зарегистрирован в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="cff15-105">HTTP transport security requires an SSL certificate to be registered with IIS.</span></span> <span data-ttu-id="cff15-106">Если SSL-сертификат не установлен, для создания тестового сертификата можно использовать службы IIS.</span><span class="sxs-lookup"><span data-stu-id="cff15-106">If you do not have an SSL certificate you can use IIS to generate a test certificate.</span></span> <span data-ttu-id="cff15-107">Затем необходимо добавить SSL-привязку для проекта веб-сайта и установить свойства проверки подлинности веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="cff15-107">Next you must add an SSL binding to the web site and configure the web site’s authentication properties.</span></span> <span data-ttu-id="cff15-108">Наконец, необходимо настроить службу WCF на использование протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cff15-108">Finally you need to configure the WCF service to use HTTPS.</span></span>  
  
### <a name="creating-a-self-signed-certificate"></a><span data-ttu-id="cff15-109">Создание самозаверяющего сертификата</span><span class="sxs-lookup"><span data-stu-id="cff15-109">Creating a Self-Signed Certificate</span></span>  
  
1. <span data-ttu-id="cff15-110">Откройте диспетчер служб IIS (inetmgr.exe) и выберите имя компьютера в левой части представления в виде дерева.</span><span class="sxs-lookup"><span data-stu-id="cff15-110">Open Internet Information Services Manager (inetmgr.exe), and select your computer name in the left-hand tree view.</span></span> <span data-ttu-id="cff15-111">В правой части экрана выберите сертификаты сервера</span><span class="sxs-lookup"><span data-stu-id="cff15-111">On the right-hand side of the screen select Server Certificates</span></span>  
  
     <span data-ttu-id="cff15-112">![Начальный экран диспетчера IIS](media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span><span class="sxs-lookup"><span data-stu-id="cff15-112">![IIS Manager Home Screen](media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span></span>  
  
2. <span data-ttu-id="cff15-113">В окне сертификаты сервера щелкните **создать самозаверяющий сертификат...** .</span><span class="sxs-lookup"><span data-stu-id="cff15-113">In the Server Certificates window click the **Create Self-Signed Certificate….**</span></span> <span data-ttu-id="cff15-114">Связь.</span><span class="sxs-lookup"><span data-stu-id="cff15-114">Link.</span></span>  
  
     <span data-ttu-id="cff15-115">![Создание&#45;самозаверяющего сертификата, подписанного с помощью служб IIS](media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span><span class="sxs-lookup"><span data-stu-id="cff15-115">![Creating a self&#45;signed certificate with IIS](media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span></span>  
  
3. <span data-ttu-id="cff15-116">Введите понятное имя самозаверяющего сертификата и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cff15-116">Enter a friendly name for the self-signed certificate and click **OK**.</span></span>  
  
     <span data-ttu-id="cff15-117">![Диалоговое окно создания самозаверяющего сертификата&#45;](media/mg-mycert.jpg "mg_MyCert")</span><span class="sxs-lookup"><span data-stu-id="cff15-117">![Create Self&#45;Signed Certificate Dialog](media/mg-mycert.jpg "mg_MyCert")</span></span>  
  
     <span data-ttu-id="cff15-118">В окне **Сертификаты сервера** теперь отображаются только что созданные самозаверяющие сертификаты.</span><span class="sxs-lookup"><span data-stu-id="cff15-118">The newly created self-signed certificate details are now shown in the **Server Certificates** window.</span></span>  
  
     <span data-ttu-id="cff15-119">![Окно "Сертификат сервера"](media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span><span class="sxs-lookup"><span data-stu-id="cff15-119">![Server Certificate Window](media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span></span>  
  
     <span data-ttu-id="cff15-120">Созданный сертификат устанавливается в хранилище доверенных корневых центров сертификации.</span><span class="sxs-lookup"><span data-stu-id="cff15-120">The generated certificate is installed in the Trusted Root Certification Authorities store.</span></span>  
  
### <a name="add-ssl-binding"></a><span data-ttu-id="cff15-121">Добавление привязки SSL</span><span class="sxs-lookup"><span data-stu-id="cff15-121">Add SSL Binding</span></span>  
  
1. <span data-ttu-id="cff15-122">По-прежнему в службы IIS Manager разверните папку **сайты** , а затем папку **веб-сайт по умолчанию** в древовидном представлении в левой части экрана.</span><span class="sxs-lookup"><span data-stu-id="cff15-122">Still in Internet Information Services Manager, expand the **Sites** folder and then the **Default Web Site** folder in the tree view on the left-hand side of the screen.</span></span>  
  
2. <span data-ttu-id="cff15-123">Щелкните **привязки....**</span><span class="sxs-lookup"><span data-stu-id="cff15-123">Click the **Bindings….**</span></span> <span data-ttu-id="cff15-124">Ссылка в разделе **действия** в верхней правой части окна.</span><span class="sxs-lookup"><span data-stu-id="cff15-124">Link in the **Actions** section in the upper right hand portion of the window.</span></span>  
  
     <span data-ttu-id="cff15-125">![Добавление привязки SSL](media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span><span class="sxs-lookup"><span data-stu-id="cff15-125">![Adding an SSL binding](media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span></span>  
  
3. <span data-ttu-id="cff15-126">В окне "привязки сайта" нажмите кнопку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="cff15-126">In the Site Bindings window click the **Add** button.</span></span>  
  
     <span data-ttu-id="cff15-127">![Диалоговое окно "Привязки сайта"](media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span><span class="sxs-lookup"><span data-stu-id="cff15-127">![Site Bindings Dialog](media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span></span>  
  
4. <span data-ttu-id="cff15-128">В диалоговом окне **Добавление привязки сайта** выберите HTTPS для типа и понятное имя самозаверяющего сертификата, который вы только что создали.</span><span class="sxs-lookup"><span data-stu-id="cff15-128">In the **Add Site Binding** dialog, select https for the type and the friendly name of the self-signed certificate you just created.</span></span>  
  
     <span data-ttu-id="cff15-129">![Пример привязки сайта](media/mg-mycertbinding.jpg "mg_MyCertBinding")</span><span class="sxs-lookup"><span data-stu-id="cff15-129">![Site binding example](media/mg-mycertbinding.jpg "mg_MyCertBinding")</span></span>  
  
### <a name="configure-virtual-directory-for-ssl"></a><span data-ttu-id="cff15-130">Настройка виртуального каталога для SSL</span><span class="sxs-lookup"><span data-stu-id="cff15-130">Configure Virtual Directory for SSL</span></span>  
  
1. <span data-ttu-id="cff15-131">В диспетчере служб IIS выберите виртуальный каталог, содержащий безопасную службу WCF.</span><span class="sxs-lookup"><span data-stu-id="cff15-131">Still in Internet Information Services Manager, select the virtual directory that contains your WCF secure service.</span></span>  
  
2. <span data-ttu-id="cff15-132">В центральной области окна выберите **Параметры SSL** в разделе IIS.</span><span class="sxs-lookup"><span data-stu-id="cff15-132">In the center pane of the window, select **SSL Settings** in the IIS section.</span></span>  
  
     <span data-ttu-id="cff15-133">![Параметры SSL для виртуального каталога](media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span><span class="sxs-lookup"><span data-stu-id="cff15-133">![SSL Settings for virtual directory](media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span></span>  
  
3. <span data-ttu-id="cff15-134">В области Параметры SSL установите флажок **требовать SSL** и щелкните ссылку **Применить** в разделе **действия** в правой части экрана.</span><span class="sxs-lookup"><span data-stu-id="cff15-134">In the SSL Settings pane, select the **Require SSL** checkbox and click the **Apply** link in the **Actions** section on the right hand side of the screen.</span></span>  
  
     <span data-ttu-id="cff15-135">![Параметры SSL виртуального каталога](media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span><span class="sxs-lookup"><span data-stu-id="cff15-135">![Virtual directory SSL settings](media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span></span>  
  
### <a name="configure-wcf-service-for-http-transport-security"></a><span data-ttu-id="cff15-136">Настройка службы WCF для безопасности транспорта HTTP</span><span class="sxs-lookup"><span data-stu-id="cff15-136">Configure WCF Service for HTTP Transport Security</span></span>  
  
1. <span data-ttu-id="cff15-137">В файле web.config службы WCF настройте привязку HTTP на использование безопасности транспорта, как показано в следующем фрагменте XML.</span><span class="sxs-lookup"><span data-stu-id="cff15-137">In the WCF service’s web.config configure the HTTP binding to use transport security as shown in the following XML.</span></span>  
  
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
  
2. <span data-ttu-id="cff15-138">Укажите службу и конечную точку службы, как показано в следующем фрагменте XML.</span><span class="sxs-lookup"><span data-stu-id="cff15-138">Specify your service and service endpoint as shown in the following XML.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="cff15-139">Пример</span><span class="sxs-lookup"><span data-stu-id="cff15-139">Example</span></span>  
 <span data-ttu-id="cff15-140">Ниже приведен полный пример файла web.config для службы WCF, использующей безопасность транспорта HTTP</span><span class="sxs-lookup"><span data-stu-id="cff15-140">The following is a complete example of a web.config file for a WCF service using HTTP transport security</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cff15-141">См. также</span><span class="sxs-lookup"><span data-stu-id="cff15-141">See also</span></span>

- [<span data-ttu-id="cff15-142">Размещение в службах IIS</span><span class="sxs-lookup"><span data-stu-id="cff15-142">Hosting in Internet Information Services</span></span>](hosting-in-internet-information-services.md)
- [<span data-ttu-id="cff15-143">Инструкции по размещению в службах IIS</span><span class="sxs-lookup"><span data-stu-id="cff15-143">Internet Information Service Hosting Instructions</span></span>](../samples/internet-information-service-hosting-instructions.md)
- [<span data-ttu-id="cff15-144">Рекомендации по размещению в службах IIS</span><span class="sxs-lookup"><span data-stu-id="cff15-144">Internet Information Services Hosting Best Practices</span></span>](internet-information-services-hosting-best-practices.md)
- [<span data-ttu-id="cff15-145">Размещение в службах IIS с использованием встроенного кода</span><span class="sxs-lookup"><span data-stu-id="cff15-145">IIS Hosting Using Inline Code</span></span>](../samples/iis-hosting-using-inline-code.md)
