---
title: <reliableSession>
ms.date: 03/30/2017
ms.assetid: 129b4a59-37f0-4030-b664-03795d257d29
ms.openlocfilehash: 95f6646041dc2dd7bae7691a0a9f748c844f50b6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738746"
---
# \<reliableSession>
<span data-ttu-id="75844-101">Определяет параметры протокола WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="75844-101">Defines setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="75844-102">Когда этот элемент добавляется к пользовательской привязке, получаемый канал может поддерживать гарантии доставки только один раз.</span><span class="sxs-lookup"><span data-stu-id="75844-102">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<reliableSession>**  
  
## <a name="syntax"></a><span data-ttu-id="75844-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75844-103">Syntax</span></span>  
  
```xml  
<reliableSession acknowledgementInterval="TimeSpan"
                 flowControlEnabled="Boolean"
                 inactivityTimeout="TimeSpan"
                 maxPendingChannels="Integer"
                 maxRetryCount="Integer"
                 maxTransferWindowSize="Integer"
                 reliableMessagingVersion="Default/WSReliableMessagingFebruary2005/WSReliableMessaging11"
                 ordered="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75844-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="75844-104">Attributes and Elements</span></span>  
 <span data-ttu-id="75844-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="75844-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75844-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="75844-106">Attributes</span></span>  
  
|<span data-ttu-id="75844-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="75844-107">Attribute</span></span>|<span data-ttu-id="75844-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="75844-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75844-109">acknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="75844-109">acknowledgementInterval</span></span>|<span data-ttu-id="75844-110">Атрибут <xref:System.TimeSpan> задает максимальный временной интервал, в течение которого канал ожидает перед отправлением уведомления о сообщениях, которые уже приняты к этому времени.</span><span class="sxs-lookup"><span data-stu-id="75844-110">A <xref:System.TimeSpan> that contains the maximum time interval the channel is going to wait to send an acknowledgment for messages received up to that point.</span></span> <span data-ttu-id="75844-111">Значение по умолчанию - 00:00:0.2.</span><span class="sxs-lookup"><span data-stu-id="75844-111">The default is 00:00:0.2.</span></span>|  
|<span data-ttu-id="75844-112">flowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="75844-112">flowControlEnabled</span></span>|<span data-ttu-id="75844-113">Логическое значение, которое указывает, активировано ли расширенное управление потоком, то есть собственная реализация Microsoft управления потоком для WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="75844-113">A Boolean value that indicates whether advanced flow control, a Microsoft-specific implementation of flow control for WS-Reliable messaging, is activated.</span></span> <span data-ttu-id="75844-114">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="75844-114">The default is `true`.</span></span>|  
|<span data-ttu-id="75844-115">inactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="75844-115">inactivityTimeout</span></span>|<span data-ttu-id="75844-116">Атрибут <xref:System.TimeSpan> указывает максимальную длительность, в течение которой канал позволяет другим участникам соединения не отправлять никаких сообщений, до закрытия канала с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="75844-116">A <xref:System.TimeSpan> that specifies the maximum duration that the channel is going to allow the other communication party not to send any messages, before faulting the channel.</span></span> <span data-ttu-id="75844-117">Значение по умолчанию - 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="75844-117">The default is 00:10:00.</span></span><br /><br /> <span data-ttu-id="75844-118">Под активностью канала понимается получение сообщений от приложения или инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="75844-118">Activity on a channel is defined as receiving an application or infrastructure messages.</span></span> <span data-ttu-id="75844-119">Данное свойство задает максимальный промежуток времени, в течение которого поддерживается неактивный сеанс.</span><span class="sxs-lookup"><span data-stu-id="75844-119">This property controls the maximum amount of time to keep an inactive session alive.</span></span> <span data-ttu-id="75844-120">Если период неактивности превышает установленное ограничение, сеанс прерывается инфраструктурой, и канал закрывается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="75844-120">If longer time passes with no activity, the session is aborted by the infrastructure and the channel faults.</span></span> <span data-ttu-id="75844-121">**Примечание.**  Приложение не является обязательным для периодической отправки сообщений, чтобы поддерживать подключение.</span><span class="sxs-lookup"><span data-stu-id="75844-121">**Note:**  It is not necessary for the application to periodically send messages to keep the connection alive.</span></span>|  
|<span data-ttu-id="75844-122">maxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="75844-122">maxPendingChannels</span></span>|<span data-ttu-id="75844-123">Целое число, задающее максимальное число каналов, ожидающих принятия на прослушивателе.</span><span class="sxs-lookup"><span data-stu-id="75844-123">An integer that specifies the maximum number of channels that can wait on the listener to be accepted.</span></span> <span data-ttu-id="75844-124">Это значение должно быть в диапазоне от 1 до 16 384 включительно.</span><span class="sxs-lookup"><span data-stu-id="75844-124">This value should be between 1 to 16384 inclusive.</span></span> <span data-ttu-id="75844-125">Значение по умолчанию — 4.</span><span class="sxs-lookup"><span data-stu-id="75844-125">The default is 4.</span></span><br /><br /> <span data-ttu-id="75844-126">Каналы находятся в режиме ожидания перед принятием.</span><span class="sxs-lookup"><span data-stu-id="75844-126">Channels are pending when they are waiting to be accepted.</span></span> <span data-ttu-id="75844-127">По достижении этого предела каналы больше не создаются.</span><span class="sxs-lookup"><span data-stu-id="75844-127">Once that limit is reached, no channels are created.</span></span> <span data-ttu-id="75844-128">Вместо этого они переводятся в режим ожидания до тех пор, пока их число не снизится (по мере принятия ожидающих каналов).</span><span class="sxs-lookup"><span data-stu-id="75844-128">Rather, they are put in pending mode until this number goes down (by accepting pending channels).</span></span> <span data-ttu-id="75844-129">Этот предел задается отдельно для каждой фабрики.</span><span class="sxs-lookup"><span data-stu-id="75844-129">This is a per-factory limit.</span></span><br /><br /> <span data-ttu-id="75844-130">Когда достигается пороговое значение и удаленное приложение пытается установить новый надежный сеанс, запрос отклоняется, и открытая операция, инициировавшая запрос, завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="75844-130">When the threshold is reached and a remote application tries to establish a new reliable session, the request is denied and the open operation that prompted this faults.</span></span> <span data-ttu-id="75844-131">Данное ограничение не действует в отношении числа ожидающих исходящих каналов.</span><span class="sxs-lookup"><span data-stu-id="75844-131">This limit does not apply to the number of pending outgoing channels.</span></span>|  
|<span data-ttu-id="75844-132">maxRetryCount</span><span class="sxs-lookup"><span data-stu-id="75844-132">maxRetryCount</span></span>|<span data-ttu-id="75844-133">Целое число, которое определяет максимальное количество попыток повторной передачи надежным каналом сообщения, для которого не было получено подтверждение приема. Повторная передача осуществляется посредством вызова функции Send в основном канале.</span><span class="sxs-lookup"><span data-stu-id="75844-133">An integer that specifies the maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgment for, by calling Send on its underlying channel.</span></span><br /><br /> <span data-ttu-id="75844-134">Значение должно быть больше нуля.</span><span class="sxs-lookup"><span data-stu-id="75844-134">This value should be greater than zero.</span></span> <span data-ttu-id="75844-135">Значение по умолчанию — 8.</span><span class="sxs-lookup"><span data-stu-id="75844-135">The default is 8.</span></span><br /><br /> <span data-ttu-id="75844-136">Значение должно целым числом больше нуля.</span><span class="sxs-lookup"><span data-stu-id="75844-136">This value should be an integer greater than zero.</span></span> <span data-ttu-id="75844-137">Если подтверждение приема не будет получено после последней попытки повторной передачи, канал закрывается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="75844-137">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="75844-138">Сообщение считается переданным, если получатель подтвердил получение этого сообщения, отправив соответствующее подтверждение отправителю.</span><span class="sxs-lookup"><span data-stu-id="75844-138">A message is considered to be transferred if its delivery at the recipient has been acknowledged by the recipient.</span></span><br /><br /> <span data-ttu-id="75844-139">Если для переданного сообщения уведомление не было получено в течение отведенного времени, инфраструктура автоматически передает сообщение повторно.</span><span class="sxs-lookup"><span data-stu-id="75844-139">If an acknowledgment has not been received within a certain amount of time for a message that has been transmitted, the infrastructure automatically retransmits the message.</span></span> <span data-ttu-id="75844-140">Количество попыток, предпринимаемых инфраструктурой для повторной передачи сообщения, не превышает того значения, которое задано данным свойством.</span><span class="sxs-lookup"><span data-stu-id="75844-140">The infrastructure tries to resend the message for at most the number of times specified by this property.</span></span> <span data-ttu-id="75844-141">Если подтверждение приема не будет получено после последней попытки повторной передачи, канал закрывается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="75844-141">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="75844-142">Инфраструктура использует алгоритм с экспоненциальной задержкой для определения времени повторной передачи на основании вычисленного среднего значения времени кругового пути.</span><span class="sxs-lookup"><span data-stu-id="75844-142">The infrastructure uses an exponential back-off algorithm to determine when to retransmit, based on a computed average round-trip time.</span></span> <span data-ttu-id="75844-143">Задержка перед первой попыткой повторной передачи составляет 1 секунду, однако для каждой последующей попытки время задержки удваивается. Таким образом, временной интервал между первой и последней попытками составляет около 8,5 минут.</span><span class="sxs-lookup"><span data-stu-id="75844-143">The time initially starts at 1 second before retransmission and doubling the delay with every attempt, which results in approximately 8.5 minutes passing between the first transmission attempt and the last retransmission attempt.</span></span> <span data-ttu-id="75844-144">Время первой повторной передачи определяется с учетом вычисленного значением времени кругового пути, соответственно изменяется общая длительность всех задержек.</span><span class="sxs-lookup"><span data-stu-id="75844-144">The time for the first retransmission attempt is adjusted according to the calculated round-trip time and the resulting stretch of time that those attempts take varies accordingly.</span></span> <span data-ttu-id="75844-145">Это позволяет динамически адаптировать время между попытками повторной передачи в соответствии с условиями сети.</span><span class="sxs-lookup"><span data-stu-id="75844-145">This allows the retransmission time to dynamically adapt to varying network conditions.</span></span>|  
|<span data-ttu-id="75844-146">maxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="75844-146">maxTransferWindowSize</span></span>|<span data-ttu-id="75844-147">Целое число, задающее максимальный размер буфера.</span><span class="sxs-lookup"><span data-stu-id="75844-147">An integer that specifies the maximum size of the buffer.</span></span> <span data-ttu-id="75844-148">Допустимые значения находятся в диапазоне от 1 до 4096 включительно.</span><span class="sxs-lookup"><span data-stu-id="75844-148">Valid values are from 1 to 4096 inclusive.</span></span><br /><br /> <span data-ttu-id="75844-149">Для клиента данный атрибут определяет максимальный размер буфера, используемого надежным каналом для хранения сообщений, получение которых еще не подтверждено получателем.</span><span class="sxs-lookup"><span data-stu-id="75844-149">On the client, this attribute defines the maximum size of the buffer used by a reliable channel to hold messages not yet acknowledged by the receiver.</span></span> <span data-ttu-id="75844-150">Единицей квоты является одно сообщение.</span><span class="sxs-lookup"><span data-stu-id="75844-150">The unit of the quota is a message.</span></span> <span data-ttu-id="75844-151">Если буфер полон, дальнейшее выполнение операций SEND блокируется.</span><span class="sxs-lookup"><span data-stu-id="75844-151">If the buffer is full, further SEND operations are blocked.</span></span><br /><br /> <span data-ttu-id="75844-152">Для получателя этот атрибут определяет максимальный размер буфера, используемого каналом для хранения входящих сообщений, которые еще не переданы приложению.</span><span class="sxs-lookup"><span data-stu-id="75844-152">On the receiver, this attribute defines the maximum size of the buffer used by the channel to store incoming messages not yet dispatched to the application.</span></span> <span data-ttu-id="75844-153">Если буфер заполнен, поступающие сообщения автоматически отбрасываются получателем и требуют повторной передачи со стороны клиента.</span><span class="sxs-lookup"><span data-stu-id="75844-153">If the buffer is full, further messages are silently dropped by the receiver and require retransmission by the client.</span></span>|  
|<span data-ttu-id="75844-154">упорядоченного</span><span class="sxs-lookup"><span data-stu-id="75844-154">ordered</span></span>|<span data-ttu-id="75844-155">Логическое значение, определяющее, прибывают ли сообщения точно в том порядке, в котором они были отправлены.</span><span class="sxs-lookup"><span data-stu-id="75844-155">A Boolean that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span> <span data-ttu-id="75844-156">Если данному атрибуту присвоено значение `false`, порядок получения сообщений может не соблюдаться.</span><span class="sxs-lookup"><span data-stu-id="75844-156">If this setting is `false`, messages can arrive out of order.</span></span> <span data-ttu-id="75844-157">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="75844-157">The default is `true`.</span></span>|  
|<span data-ttu-id="75844-158">reliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="75844-158">reliableMessagingVersion</span></span>|<span data-ttu-id="75844-159">Допустимое значение из <xref:System.ServiceModel.ReliableMessagingVersion>, задающее версию используемого протокола WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="75844-159">A valid value from <xref:System.ServiceModel.ReliableMessagingVersion> that specifies the WS-ReliableMessaging version to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75844-160">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="75844-160">Child Elements</span></span>  
 <span data-ttu-id="75844-161">Нет</span><span class="sxs-lookup"><span data-stu-id="75844-161">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75844-162">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="75844-162">Parent Elements</span></span>  
  
|<span data-ttu-id="75844-163">Элемент</span><span class="sxs-lookup"><span data-stu-id="75844-163">Element</span></span>|<span data-ttu-id="75844-164">Описание</span><span class="sxs-lookup"><span data-stu-id="75844-164">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="75844-165">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="75844-165">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75844-166">Примечания</span><span class="sxs-lookup"><span data-stu-id="75844-166">Remarks</span></span>  
 <span data-ttu-id="75844-167">Надежные сеансы обеспечивают возможности для надежного обмена сообщениями и сеансов.</span><span class="sxs-lookup"><span data-stu-id="75844-167">Reliable sessions provide features for reliable messaging and sessions.</span></span> <span data-ttu-id="75844-168">При надежном обмене сообщениями в случае сбоя предпринимается повторная попытка передачи, и можно задать такие гарантии доставки, как соблюдение порядка получения сообщений.</span><span class="sxs-lookup"><span data-stu-id="75844-168">Reliable messaging retries communication on failure and allows delivery assurances such as in-order arrival of messages to be specified.</span></span> <span data-ttu-id="75844-169">Сеансы поддерживают состояние для клиентов между вызовами.</span><span class="sxs-lookup"><span data-stu-id="75844-169">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="75844-170">Этот элемент также дополнительно предоставляет упорядоченную доставку сообщений.</span><span class="sxs-lookup"><span data-stu-id="75844-170">This element also optionally provides ordered message delivery.</span></span> <span data-ttu-id="75844-171">Эта реализация сеанса может использоваться в контексте посредников SOAP и транспорта.</span><span class="sxs-lookup"><span data-stu-id="75844-171">This implemented session can cross SOAP and transport intermediaries.</span></span>  
  
 <span data-ttu-id="75844-172">Каждый элемент привязки представляет собой этап обработки при отправке или получении сообщений.</span><span class="sxs-lookup"><span data-stu-id="75844-172">Each binding element represents a processing step when sending or receiving messages.</span></span> <span data-ttu-id="75844-173">Во время выполнения элементы привязки создают фабрики и прослушиватели каналов, которые нужны для построения стеков исходящих и входящих каналов, необходимых для приема и передачи сообщений.</span><span class="sxs-lookup"><span data-stu-id="75844-173">At runtime, binding elements create the channel factories and listeners that are necessary to build outgoing and incoming channel stacks required to send and receive messages.</span></span> <span data-ttu-id="75844-174">Элемент `reliableSession` предоставляет дополнительный уровень в стеке, который может установить надежный сеанс между конечными точками и настроить поведение этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="75844-174">The `reliableSession` provides an optional layer in the stack that can establish a reliable session between endpoints and configure the behavior of this session.</span></span>  
  
 <span data-ttu-id="75844-175">Дополнительные сведения см. в разделе [Надежные сеансы](../../../wcf/feature-details/reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="75844-175">For more information, see [Reliable Sessions](../../../wcf/feature-details/reliable-sessions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="75844-176">Пример</span><span class="sxs-lookup"><span data-stu-id="75844-176">Example</span></span>  
 <span data-ttu-id="75844-177">В следующем примере показано, как настраивать пользовательскую привязку с различными элементами транспорта и кодирования сообщений, а именно: с обеспечением надежных сеансов, которые поддерживают состояние клиента и задают гарантии соблюдения очередности доставки сообщений.</span><span class="sxs-lookup"><span data-stu-id="75844-177">The following example demonstrates how to configure a custom binding with various transport and message encoding elements, especially enabling reliable sessions, which maintains client state and specifies in-order delivery assurances.</span></span> <span data-ttu-id="75844-178">Эта функция настраивается в файлах конфигурации приложения для клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="75844-178">This feature is configured in the application configuration files for the client and service.</span></span> <span data-ttu-id="75844-179">В следующем примере демонстрируется конфигурация службы.</span><span class="sxs-lookup"><span data-stu-id="75844-179">The example show the service configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc -->
        <!-- specify customBinding binding and a binding configuration to use -->
        <endpoint address=""
                  binding="customBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <!-- custom binding configuration - configures HTTP transport, reliable sessions -->
    <bindings>
      <customBinding>
        <binding name="Binding1">
          <reliableSession />
          <security authenticationMode="SecureConversation"
                    requireSecurityContextCancellation="true">
          </security>
          <compositeDuplex />
          <oneWay />
          <textMessageEncoding messageVersion="Soap12WSAddressing10"
                               writeEncoding="utf-8" />
          <httpTransport authenticationScheme="Anonymous"
                         bypassProxyOnLocal="false"
                         hostNameComparisonMode="StrongWildcard"
                         proxyAuthenticationScheme="Anonymous"
                         realm=""
                         useDefaultWebProxy="true" />
        </binding>
      </customBinding>
    </bindings>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="75844-180">См. также</span><span class="sxs-lookup"><span data-stu-id="75844-180">See also</span></span>

- <xref:System.ServiceModel.Configuration.ReliableSessionElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
- [<span data-ttu-id="75844-181">Надежные сеансы</span><span class="sxs-lookup"><span data-stu-id="75844-181">Reliable Sessions</span></span>](../../../wcf/feature-details/reliable-sessions.md)
- [<span data-ttu-id="75844-182">Привязки</span><span class="sxs-lookup"><span data-stu-id="75844-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="75844-183">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="75844-183">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="75844-184">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="75844-184">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
