---
title: Настраиваемое действие SendMail
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: 4dca15bfd3798b9282960663bea827f9323a1266
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547744"
---
# <a name="sendmail-custom-activity"></a><span data-ttu-id="edae7-102">Настраиваемое действие SendMail</span><span class="sxs-lookup"><span data-stu-id="edae7-102">SendMail Custom Activity</span></span>
<span data-ttu-id="edae7-103">В образце описывается создание настраиваемого действия, которое является производным от <xref:System.Activities.AsyncCodeActivity>, для отправки почты с помощью SMTP для работы в приложении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="edae7-103">This sample demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span> <span data-ttu-id="edae7-104">Настраиваемое действие использует возможности <xref:System.Net.Mail.SmtpClient> для асинхронной отправки электронной почты и отправки почты с проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="edae7-104">The custom activity uses the capabilities of <xref:System.Net.Mail.SmtpClient> to send email asynchronously and to send mail with authentication.</span></span> <span data-ttu-id="edae7-105">При этом также обеспечивается возможность использования таких возможностей конечных пользователей, как тестовый режим, замена маркеров, шаблоны файлов и тестовый путь размещения файла.</span><span class="sxs-lookup"><span data-stu-id="edae7-105">It also provides some end-user features like test mode, token replacement, file templates, and test drop path.</span></span>  
  
 <span data-ttu-id="edae7-106">В следующей таблице представлены аргументы для действия `SendMail`.</span><span class="sxs-lookup"><span data-stu-id="edae7-106">The following table details the arguments for the `SendMail` activity.</span></span>  
  
|<span data-ttu-id="edae7-107">Имя</span><span class="sxs-lookup"><span data-stu-id="edae7-107">Name</span></span>|<span data-ttu-id="edae7-108">Type</span><span class="sxs-lookup"><span data-stu-id="edae7-108">Type</span></span>|<span data-ttu-id="edae7-109">Описание</span><span class="sxs-lookup"><span data-stu-id="edae7-109">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="edae7-110">Узел</span><span class="sxs-lookup"><span data-stu-id="edae7-110">Host</span></span>|<span data-ttu-id="edae7-111">Строка</span><span class="sxs-lookup"><span data-stu-id="edae7-111">String</span></span>|<span data-ttu-id="edae7-112">Адрес узла SMTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="edae7-112">Address of the SMTP server host.</span></span>|  
|<span data-ttu-id="edae7-113">Port</span><span class="sxs-lookup"><span data-stu-id="edae7-113">Port</span></span>|<span data-ttu-id="edae7-114">Строка</span><span class="sxs-lookup"><span data-stu-id="edae7-114">String</span></span>|<span data-ttu-id="edae7-115">Порт службы SMTP на узле.</span><span class="sxs-lookup"><span data-stu-id="edae7-115">Port of the SMTP service in the host.</span></span>|  
|<span data-ttu-id="edae7-116">EnableSsl</span><span class="sxs-lookup"><span data-stu-id="edae7-116">EnableSsl</span></span>|<span data-ttu-id="edae7-117">bool</span><span class="sxs-lookup"><span data-stu-id="edae7-117">bool</span></span>|<span data-ttu-id="edae7-118">Указывает, использует ли <xref:System.Net.Mail.SmtpClient> протокол SSL для шифрования соединения.</span><span class="sxs-lookup"><span data-stu-id="edae7-118">Specifies whether the <xref:System.Net.Mail.SmtpClient> uses Secure Sockets Layer (SSL) to encrypt the connection.</span></span>|  
|<span data-ttu-id="edae7-119">UserName</span><span class="sxs-lookup"><span data-stu-id="edae7-119">UserName</span></span>|<span data-ttu-id="edae7-120">Строка</span><span class="sxs-lookup"><span data-stu-id="edae7-120">String</span></span>|<span data-ttu-id="edae7-121">Имя пользователя для настройки учетных данных для проверки подлинности свойства <xref:System.Net.Mail.SmtpClient.Credentials%2A> отправителя.</span><span class="sxs-lookup"><span data-stu-id="edae7-121">Username to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="edae7-122">Пароль</span><span class="sxs-lookup"><span data-stu-id="edae7-122">Password</span></span>|<span data-ttu-id="edae7-123">Строка</span><span class="sxs-lookup"><span data-stu-id="edae7-123">String</span></span>|<span data-ttu-id="edae7-124">Пароль для настройки учетных данных для проверки подлинности свойства <xref:System.Net.Mail.SmtpClient.Credentials%2A> отправителя.</span><span class="sxs-lookup"><span data-stu-id="edae7-124">Password to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="edae7-125">Субъект</span><span class="sxs-lookup"><span data-stu-id="edae7-125">Subject</span></span>|<xref:System.Activities.InArgument%601>\<string>|<span data-ttu-id="edae7-126">Тема сообщения.</span><span class="sxs-lookup"><span data-stu-id="edae7-126">Subject of the message.</span></span>|  
|<span data-ttu-id="edae7-127">Текст</span><span class="sxs-lookup"><span data-stu-id="edae7-127">Body</span></span>|<xref:System.Activities.InArgument%601>\<string>|<span data-ttu-id="edae7-128">Текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="edae7-128">Body of the message.</span></span>|  
|<span data-ttu-id="edae7-129">Вложения</span><span class="sxs-lookup"><span data-stu-id="edae7-129">Attachments</span></span>|<xref:System.Activities.InArgument%601>\<string>|<span data-ttu-id="edae7-130">Коллекция вложений, используемая для хранения данных, вложенных в это сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="edae7-130">Attachment collection used to store data attached to this email message.</span></span>|  
|<span data-ttu-id="edae7-131">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="edae7-131">From</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="edae7-132">Адрес для этого сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="edae7-132">From address for this email message.</span></span>|  
|<span data-ttu-id="edae7-133">Кому</span><span class="sxs-lookup"><span data-stu-id="edae7-133">To</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="edae7-134">Коллекция адресов, содержащая получателей данного сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="edae7-134">Address collection that contains the recipients of this email message.</span></span>|  
|<span data-ttu-id="edae7-135">CC</span><span class="sxs-lookup"><span data-stu-id="edae7-135">CC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="edae7-136">Коллекция адресов, содержащая получателей копии (CC) для данного сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="edae7-136">Address collection that contains the carbon copy (CC) recipients for this email message.</span></span>|  
|<span data-ttu-id="edae7-137">BCC</span><span class="sxs-lookup"><span data-stu-id="edae7-137">BCC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="edae7-138">Коллекция адресов, содержащая получателей скрытой копии (BCC) для данного сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="edae7-138">Address collection that contains the blind carbon copy (BCC) recipients for this email message.</span></span>|  
|<span data-ttu-id="edae7-139">Токены</span><span class="sxs-lookup"><span data-stu-id="edae7-139">Tokens</span></span>|<span data-ttu-id="edae7-140"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span><span class="sxs-lookup"><span data-stu-id="edae7-140"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span></span>|<span data-ttu-id="edae7-141">Маркеры для замены в тексте.</span><span class="sxs-lookup"><span data-stu-id="edae7-141">Tokens to replace in the body.</span></span> <span data-ttu-id="edae7-142">Эта возможность позволяет пользователям указывать определенные значением в тексте сообщения, которые можно позднее заменить маркерами, предоставляемыми при использовании этого свойства.</span><span class="sxs-lookup"><span data-stu-id="edae7-142">This feature allows users to specify some values in the body than can be replaced later by the tokens provided using this property.</span></span>|  
|<span data-ttu-id="edae7-143">BodyTemplateFilePath</span><span class="sxs-lookup"><span data-stu-id="edae7-143">BodyTemplateFilePath</span></span>|<span data-ttu-id="edae7-144">Строка</span><span class="sxs-lookup"><span data-stu-id="edae7-144">String</span></span>|<span data-ttu-id="edae7-145">Путь к шаблону текста.</span><span class="sxs-lookup"><span data-stu-id="edae7-145">Path of a template for the body.</span></span> <span data-ttu-id="edae7-146">Действие `SendMail` копирует содержимое этого файла в свойство текста.</span><span class="sxs-lookup"><span data-stu-id="edae7-146">The `SendMail` activity copies the contents of this file to its body property.</span></span><br /><br /> <span data-ttu-id="edae7-147">Этот шаблон может содержать токены, которые заменяются на содержимое свойства Tokens.</span><span class="sxs-lookup"><span data-stu-id="edae7-147">The template can contain tokens that are replaced by the contents of the tokens property.</span></span>|  
|<span data-ttu-id="edae7-148">TestMailTo</span><span class="sxs-lookup"><span data-stu-id="edae7-148">TestMailTo</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="edae7-149">Если это свойство задано, все сообщения электронной почты отправляются по адресу, указанному в нем.</span><span class="sxs-lookup"><span data-stu-id="edae7-149">When this property is set, all emails are sent to the address specified in it.</span></span><br /><br /> <span data-ttu-id="edae7-150">Это свойство планируется использовать при тестировании рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="edae7-150">This property is intended to be used when testing workflows.</span></span> <span data-ttu-id="edae7-151">Например, если нужно убедиться, что все сообщения электронной почты отправляются без отправки их реальным получателям.</span><span class="sxs-lookup"><span data-stu-id="edae7-151">For example, when you want to make sure that all emails are sent without sending them to the actual recipients.</span></span>|  
|<span data-ttu-id="edae7-152">TestDropPath</span><span class="sxs-lookup"><span data-stu-id="edae7-152">TestDropPath</span></span>|<span data-ttu-id="edae7-153">Строка</span><span class="sxs-lookup"><span data-stu-id="edae7-153">String</span></span>|<span data-ttu-id="edae7-154">Если это свойство задано, все сообщения электронной почты также сохраняются в указанном файле.</span><span class="sxs-lookup"><span data-stu-id="edae7-154">When this property is set, all emails are also saved in the specified file.</span></span><br /><br /> <span data-ttu-id="edae7-155">Это свойство предназначено для использования при тестировании или отладке рабочих процессов, чтобы убедиться в правильности формата и содержимого исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="edae7-155">This property is intended to be used when you are testing or debugging workflows, to make sure that the format and contents of the outgoing emails is appropriate.</span></span>|  
  
## <a name="solution-contents"></a><span data-ttu-id="edae7-156">Содержимое решения</span><span class="sxs-lookup"><span data-stu-id="edae7-156">Solution Contents</span></span>  
 <span data-ttu-id="edae7-157">Решение содержит два проекта.</span><span class="sxs-lookup"><span data-stu-id="edae7-157">The solution contains two projects.</span></span>  
  
|<span data-ttu-id="edae7-158">Проект</span><span class="sxs-lookup"><span data-stu-id="edae7-158">Project</span></span>|<span data-ttu-id="edae7-159">Описание</span><span class="sxs-lookup"><span data-stu-id="edae7-159">Description</span></span>|<span data-ttu-id="edae7-160">Важные файлы</span><span class="sxs-lookup"><span data-stu-id="edae7-160">Important Files</span></span>|  
|-------------|-----------------|---------------------|  
|<span data-ttu-id="edae7-161">SendMail</span><span class="sxs-lookup"><span data-stu-id="edae7-161">SendMail</span></span>|<span data-ttu-id="edae7-162">Действие SendMail</span><span class="sxs-lookup"><span data-stu-id="edae7-162">The SendMail activity</span></span>|<span data-ttu-id="edae7-163">1. SendMail.cs: реализация для основного действия</span><span class="sxs-lookup"><span data-stu-id="edae7-163">1.  SendMail.cs: implementation for the main activity</span></span><br /><span data-ttu-id="edae7-164">2. Сендмаилдесигнер. XAML и SendMailDesigner.xaml.cs: конструктор для действия SendMail</span><span class="sxs-lookup"><span data-stu-id="edae7-164">2.  SendMailDesigner.xaml and SendMailDesigner.xaml.cs: designer for the SendMail activity</span></span><br /><span data-ttu-id="edae7-165">3. MailTemplateBody.htm: шаблон для отправляемого сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="edae7-165">3.  MailTemplateBody.htm: template for the email to be sent out.</span></span>|  
|<span data-ttu-id="edae7-166">SendMailTestClient</span><span class="sxs-lookup"><span data-stu-id="edae7-166">SendMailTestClient</span></span>|<span data-ttu-id="edae7-167">Клиент для тестирования действий SendMail.</span><span class="sxs-lookup"><span data-stu-id="edae7-167">Client to test the SendMail activity.</span></span>  <span data-ttu-id="edae7-168">В этом проекте описываются два способа вызова действия SendMail: декларативно и программно.</span><span class="sxs-lookup"><span data-stu-id="edae7-168">This project demonstrates two ways of invoking the SendMail activity: declaratively, and programmatically.</span></span>|<span data-ttu-id="edae7-169">1. Sequence1. XAML: рабочий процесс, вызывающий действие SendMail.</span><span class="sxs-lookup"><span data-stu-id="edae7-169">1.  Sequence1.xaml: workflow that invokes the SendMail activity.</span></span><br /><span data-ttu-id="edae7-170">2. Program.cs: вызывает Sequence1, а также создает рабочий процесс программным способом, использующим SendMail.</span><span class="sxs-lookup"><span data-stu-id="edae7-170">2.  Program.cs: invokes Sequence1 and also creates a workflow programmatically that uses SendMail.</span></span>|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a><span data-ttu-id="edae7-171">Дополнительная настройка действия SendMail</span><span class="sxs-lookup"><span data-stu-id="edae7-171">Further configuration of the SendMail activity</span></span>  
 <span data-ttu-id="edae7-172">Хотя она не показана в образце, пользователи могут выполнять дополнительную настройку действия SendMail.</span><span class="sxs-lookup"><span data-stu-id="edae7-172">Although not shown in the sample, users can perform addition configuration of the SendMail activity.</span></span> <span data-ttu-id="edae7-173">Эта дополнительная настройка описывается в следующих трех разделах.</span><span class="sxs-lookup"><span data-stu-id="edae7-173">The next three sections demonstrate how this is done.</span></span>  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a><span data-ttu-id="edae7-174">Отправка сообщения электронной почты с использованием маркеров, указанных в тексте сообщения</span><span class="sxs-lookup"><span data-stu-id="edae7-174">Sending an email using tokens specified in the body</span></span>  
 <span data-ttu-id="edae7-175">В этом фрагменте кода описывается отправка сообщения электронной почты с маркеров в тексте сообщения.</span><span class="sxs-lookup"><span data-stu-id="edae7-175">This code snippet demonstrates how you can send email with tokens in the body.</span></span> <span data-ttu-id="edae7-176">Обратите внимание на то, как маркеры включены в текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="edae7-176">Notice how the tokens are provided in the body property.</span></span> <span data-ttu-id="edae7-177">Значения для этих маркеров предоставлены для свойства маркеров.</span><span class="sxs-lookup"><span data-stu-id="edae7-177">Values for those tokens are provided to the tokens property.</span></span>  
  
```csharp  
IDictionary<string, string> tokens = new Dictionary<string, string>();  
tokens.Add("@name", "John Doe");  
tokens.Add("@date", DateTime.Now.ToString());  
tokens.Add("@server", "localhost");  
  
new SendMail  
{  
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Body = "Hello @name. This is a test email sent from @server. Current date is @date",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens)  
};  
```  
  
### <a name="sending-an-email-using-a-template"></a><span data-ttu-id="edae7-178">Отправка сообщения электронной почты с использованием шаблона</span><span class="sxs-lookup"><span data-stu-id="edae7-178">Sending an email using a template</span></span>  
 <span data-ttu-id="edae7-179">В этом фрагменте описывается отправка сообщения электронной почты с использованием маркеров шаблона в тексте.</span><span class="sxs-lookup"><span data-stu-id="edae7-179">This snippet shows how to send an email using a template tokens in the body.</span></span> <span data-ttu-id="edae7-180">Обратите внимание, что при задании свойства `BodyTemplateFilePath` не нужно указывать значение для свойства Body (содержимое файла шаблона будет скопировано в текст).</span><span class="sxs-lookup"><span data-stu-id="edae7-180">Notice that when setting the `BodyTemplateFilePath` property we don’t need to provide the value for Body property (the contents of the template file will be copied to the body).</span></span>  
  
```csharp  
new SendMail  
{
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
    BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",
};  
```  
  
### <a name="sending-mails-in-testing-mode"></a><span data-ttu-id="edae7-181">Отправка сообщений в тестовом режиме</span><span class="sxs-lookup"><span data-stu-id="edae7-181">Sending Mails in Testing Mode</span></span>  
 <span data-ttu-id="edae7-182">В этом фрагменте кода показано, как задать два свойства тестирования: при выборе `TestMailTo` значения все сообщения будут отправляться `john.doe@contoso.con` (без учета значений в, CC, BCC).</span><span class="sxs-lookup"><span data-stu-id="edae7-182">This code snippet shows how to set the two testing properties: by setting `TestMailTo` to all messages will be sent to `john.doe@contoso.con` (without regard of the values of To, Cc, Bcc).</span></span> <span data-ttu-id="edae7-183">При задании TestDropPath все исходящие сообщения электронной почты будут также записываться по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="edae7-183">By setting TestDropPath all outgoing emails will be also recorded in the provided path.</span></span> <span data-ttu-id="edae7-184">Эти свойства могут быть заданы независимо (они не связаны друг с другом).</span><span class="sxs-lookup"><span data-stu-id="edae7-184">These properties can be set independently (they are not related).</span></span>  
  
```csharp  
new SendMail  
{
   From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
   Subject = "Test email",  
   Host = "localhost",  
   Port = 25,  
   Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
   BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",  
   TestMailTo= new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   TestDropPath = @"c:\Samples\SendMail\TestDropPath\",  
};  
```  
  
## <a name="set-up-instructions"></a><span data-ttu-id="edae7-185">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="edae7-185">Set-Up Instructions</span></span>  
 <span data-ttu-id="edae7-186">В этом образце необходим доступ к SMTP-серверу.</span><span class="sxs-lookup"><span data-stu-id="edae7-186">Access to a SMTP server is required for this sample.</span></span>  
  
 <span data-ttu-id="edae7-187">Дополнительные сведения о настройке SMTP-сервера см. по следующим ссылкам.</span><span class="sxs-lookup"><span data-stu-id="edae7-187">For more information about setting up a SMTP server, see the following links.</span></span>  
  
- <span data-ttu-id="edae7-188">[Настройка службы SMTP (IIS 6.0)](/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="edae7-188">[Configuring the SMTP Service (IIS 6.0)](/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))</span></span>  
  
- <span data-ttu-id="edae7-189">[IIS 7.0: настройка протокола электронной почты SMTP](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="edae7-189">[IIS 7.0: Configure SMTP E-Mail](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))</span></span>  
  
- <span data-ttu-id="edae7-190">[Установка службы SMTP](/previous-versions/tn-archive/aa997480(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="edae7-190">[How to Install the SMTP Service](/previous-versions/tn-archive/aa997480(v=exchg.65))</span></span>  
  
 <span data-ttu-id="edae7-191">Эмуляторы SMTP разработки сторонних производителей можно загрузить из Интернета.</span><span class="sxs-lookup"><span data-stu-id="edae7-191">SMTP emulators provided by third parties are available for download.</span></span>  
  
##### <a name="to-run-this-sample"></a><span data-ttu-id="edae7-192">Запуск образца</span><span class="sxs-lookup"><span data-stu-id="edae7-192">To run this sample</span></span>  
  
1. <span data-ttu-id="edae7-193">Откройте в Visual Studio 2010 файл решения SendMail. sln.</span><span class="sxs-lookup"><span data-stu-id="edae7-193">Using Visual Studio 2010, open the SendMail.sln solution file.</span></span>  
  
2. <span data-ttu-id="edae7-194">Убедитесь, что имеется доступ к работающему SMTP-серверу.</span><span class="sxs-lookup"><span data-stu-id="edae7-194">Ensure that you have access to a valid SMTP server.</span></span> <span data-ttu-id="edae7-195">См. инструкции по настройке.</span><span class="sxs-lookup"><span data-stu-id="edae7-195">See the set-up instructions.</span></span>  
  
3. <span data-ttu-id="edae7-196">Настройте программу, указав адрес сервера, а также адреса электронной почты и.</span><span class="sxs-lookup"><span data-stu-id="edae7-196">Configure the program with your server address, and From and To email addresses.</span></span>  
  
     <span data-ttu-id="edae7-197">Для правильного выполнения этого примера может потребоваться настроить значение в адресах электронной почты и адресе SMTP-сервера в Program.cs и в последовательности. XAML.</span><span class="sxs-lookup"><span data-stu-id="edae7-197">To correctly run this sample, you may need to configure the value of From and To email addresses and the address of the SMTP server in  Program.cs and in Sequence.xaml.</span></span> <span data-ttu-id="edae7-198">Потребуется изменение адреса в обоих расположениях, поскольку программа отправляет сообщения двумя различными способами</span><span class="sxs-lookup"><span data-stu-id="edae7-198">You will need to change the address in both locations since the program sends mail in two different ways</span></span>  
  
4. <span data-ttu-id="edae7-199">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="edae7-199">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5. <span data-ttu-id="edae7-200">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="edae7-200">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="edae7-201">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="edae7-201">The samples may already be installed on your machine.</span></span> <span data-ttu-id="edae7-202">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="edae7-202">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="edae7-203">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="edae7-203">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="edae7-204">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="edae7-204">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
