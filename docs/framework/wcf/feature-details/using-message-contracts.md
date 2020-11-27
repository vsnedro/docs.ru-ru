---
title: Использование контрактов сообщений
description: Узнайте, как использовать атрибуты контракта сообщения для создания контракта сообщения, указывающего структуру сообщения SOAP, в WFC.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message contracts [WCF]
ms.assetid: 1e19c64a-ae84-4c2f-9155-91c54a77c249
ms.openlocfilehash: 39838ac219f095b727ad953158d54da2682a09fa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96282019"
---
# <a name="using-message-contracts"></a><span data-ttu-id="895b9-103">Использование контрактов сообщений</span><span class="sxs-lookup"><span data-stu-id="895b9-103">Using Message Contracts</span></span>

<span data-ttu-id="895b9-104">Как правило, при создании приложений Windows Communication Foundation (WCF) разработчики обращают внимание на структуры данных и проблемы сериализации и не должны беспокоиться о структуре сообщений, в которых эти данные переносятся.</span><span class="sxs-lookup"><span data-stu-id="895b9-104">Typically when building Windows Communication Foundation (WCF) applications, developers pay close attention to the data structures and serialization issues and do not need to concern themselves with the structure of the messages in which the data is carried.</span></span> <span data-ttu-id="895b9-105">Для таких приложений создание контрактов данных для параметров или возвращаемых значений представляет собой достаточно простую задачу.</span><span class="sxs-lookup"><span data-stu-id="895b9-105">For these applications, creating data contracts for the parameters or return values is straightforward.</span></span> <span data-ttu-id="895b9-106">(Дополнительные сведения см. [в разделе указание передача данных в контрактах служб](specifying-data-transfer-in-service-contracts.md).)</span><span class="sxs-lookup"><span data-stu-id="895b9-106">(For more information, see [Specifying Data Transfer in Service Contracts](specifying-data-transfer-in-service-contracts.md).)</span></span>  
  
 <span data-ttu-id="895b9-107">Тем не менее, иногда полный контроль над структурой сообщения SOAP столь же важен, сколь и контроль над его содержимым.</span><span class="sxs-lookup"><span data-stu-id="895b9-107">However, sometimes complete control over the structure of a SOAP message is just as important as control over its contents.</span></span> <span data-ttu-id="895b9-108">Это особенно актуально, если важно обеспечить взаимодействие или контролировать определенные вопросы безопасности на уровне сообщения или части сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-108">This is especially true when interoperability is important or to specifically control security issues at the level of the message or message part.</span></span> <span data-ttu-id="895b9-109">В таких случаях можно создать *контракт сообщения* , который позволяет указать структуру точного сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="895b9-109">In these cases, you can create a *message contract* that enables you to specify the structure of the precise SOAP message required.</span></span>  
  
 <span data-ttu-id="895b9-110">В этом разделе рассматривается использование различных атрибутов контрактов сообщений для создания конкретного контракта сообщения для данной операции.</span><span class="sxs-lookup"><span data-stu-id="895b9-110">This topic discusses how to use the various message contract attributes to create a specific message contract for your operation.</span></span>  
  
## <a name="using-message-contracts-in-operations"></a><span data-ttu-id="895b9-111">Использование контрактов сообщений в операциях</span><span class="sxs-lookup"><span data-stu-id="895b9-111">Using Message Contracts in Operations</span></span>  

 <span data-ttu-id="895b9-112">WCF поддерживает операции, смоделированные как в *стиле удаленного вызова процедур (RPC)* , так и в *стиле обмена сообщениями*.</span><span class="sxs-lookup"><span data-stu-id="895b9-112">WCF supports operations modeled on either the *remote procedure call (RPC) style* or the *messaging style*.</span></span> <span data-ttu-id="895b9-113">В операции в стиле RPC можно использовать любой сериализуемый тип и иметь в распоряжении возможности, доступные локальным вызовам, такие как множественные параметры и параметры `ref` и `out`.</span><span class="sxs-lookup"><span data-stu-id="895b9-113">In an RPC-style operation, you can use any serializable type, and you have access to the features that are available to local calls, such as multiple parameters and `ref` and `out` parameters.</span></span> <span data-ttu-id="895b9-114">В этом стиле выбранная форма сериализации управляет структурой данных в базовых сообщениях, а среда выполнения WCF создает сообщения для поддержки операции.</span><span class="sxs-lookup"><span data-stu-id="895b9-114">In this style, the form of serialization chosen controls the structure of the data in the underlying messages, and the WCF runtime creates the messages to support the operation.</span></span> <span data-ttu-id="895b9-115">Это позволяет разработчикам, не знакомым с протоколом SOAP и сообщениями SOAP, быстро и просто создавать и использовать приложения служб.</span><span class="sxs-lookup"><span data-stu-id="895b9-115">This enables developers who are not familiar with SOAP and SOAP messages to quickly and easily create and use service applications.</span></span>  
  
 <span data-ttu-id="895b9-116">В приведенном ниже примере кода показана операция службы, смоделированная на основе стиля RPC.</span><span class="sxs-lookup"><span data-stu-id="895b9-116">The following code example shows a service operation modeled on the RPC style.</span></span>  
  
```csharp  
[OperationContract]  
public BankingTransactionResponse PostBankingTransaction(BankingTransaction bt);  
```  
  
 <span data-ttu-id="895b9-117">Как правило, контракта данных достаточно для определения схемы для сообщений.</span><span class="sxs-lookup"><span data-stu-id="895b9-117">Normally, a data contract is sufficient to define the schema for the messages.</span></span> <span data-ttu-id="895b9-118">Например, в предыдущем примере для большинства приложений будет достаточно, если `BankingTransaction` и `BankingTransactionResponse` имеют контракты данных для определения содержимого соответствующих сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="895b9-118">For instance, in the preceding example, it is sufficient for most applications if `BankingTransaction` and `BankingTransactionResponse` have data contracts to define the contents of the underlying SOAP messages.</span></span> <span data-ttu-id="895b9-119">Дополнительные сведения о контрактах данных см. [в разделе Использование контрактов данных](using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="895b9-119">For more information about data contracts, see [Using Data Contracts](using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="895b9-120">Однако иногда необходимо точно контролировать процесс передачи структуры сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="895b9-120">However, occasionally it is necessary to precisely control how the structure of the SOAP message transmitted over the wire.</span></span> <span data-ttu-id="895b9-121">Наиболее распространенным сценарием в таком случае является вставка настраиваемых заголовков SOAP.</span><span class="sxs-lookup"><span data-stu-id="895b9-121">The most common scenario for this is inserting custom SOAP headers.</span></span> <span data-ttu-id="895b9-122">Другой часто используемый сценарий - определить свойства безопасности для заголовков и тела сообщения, т. е. решить, будут ли эти элементы снабжаться цифровой подписью и шифроваться.</span><span class="sxs-lookup"><span data-stu-id="895b9-122">Another common scenario is to define security properties for the message's headers and body, that is, to decide whether these elements are digitally signed and encrypted.</span></span> <span data-ttu-id="895b9-123">Наконец, для некоторых сторонних стеков SOAP необходимо, чтобы сообщения имели конкретный формат.</span><span class="sxs-lookup"><span data-stu-id="895b9-123">Finally, some third-party SOAP stacks require messages be in a specific format.</span></span> <span data-ttu-id="895b9-124">Такого рода контроль обеспечивается операциями в стиле сообщений.</span><span class="sxs-lookup"><span data-stu-id="895b9-124">Messaging-style operations provide this control.</span></span>  
  
 <span data-ttu-id="895b9-125">Операция в стиле сообщений имеет максимум один параметр и одно возвращаемое значение, причем оба типа являются типами сообщений, т. е. они сериализуются непосредственно в заданную структуру сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="895b9-125">A messaging-style operation has at most one parameter and one return value where both types are message types; that is, they serialize directly into a specified SOAP message structure.</span></span> <span data-ttu-id="895b9-126">Это может быть любой тип, отмеченный атрибутом <xref:System.ServiceModel.MessageContractAttribute>, или тип <xref:System.ServiceModel.Channels.Message>.</span><span class="sxs-lookup"><span data-stu-id="895b9-126">This may be any type marked with the <xref:System.ServiceModel.MessageContractAttribute> or the <xref:System.ServiceModel.Channels.Message> type.</span></span> <span data-ttu-id="895b9-127">В приведенном ниже примере кода показана операция, схожая с показанной выше операцией в стиле RPC, однако смоделированная на основе стиля сообщений.</span><span class="sxs-lookup"><span data-stu-id="895b9-127">The following code example shows an operation similar to the preceding RCP-style, but which uses the messaging style.</span></span>  
  
 <span data-ttu-id="895b9-128">Например, если и `BankingTransaction`, и `BankingTransactionResponse` представляют собой типы, являющиеся контрактами сообщений, код в следующих операциях является допустимым.</span><span class="sxs-lookup"><span data-stu-id="895b9-128">For example, if `BankingTransaction` and `BankingTransactionResponse` are both types that are message contracts, then the code in the following operations is valid.</span></span>  
  
```csharp  
[OperationContract]  
BankingTransactionResponse Process(BankingTransaction bt);  
[OperationContract]  
void Store(BankingTransaction bt);  
[OperationContract]  
BankingTransactionResponse GetResponse();  
```  
  
 <span data-ttu-id="895b9-129">В то же время следующий код является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="895b9-129">However, the following code is invalid.</span></span>  
  
```csharp  
[OperationContract]  
bool Validate(BankingTransaction bt);  
// Invalid, the return type is not a message contract.  
[OperationContract]  
void Reconcile(BankingTransaction bt1, BankingTransaction bt2);  
// Invalid, there is more than one parameter.  
```  
  
 <span data-ttu-id="895b9-130">Для каждой операции с участием типа с контрактом сообщения, не соответствующей одному из допустимых шаблонов, вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="895b9-130">An exception is thrown for any operation that involves a message contract type and that does not follow one of the valid patterns.</span></span> <span data-ttu-id="895b9-131">Конечно, на операции без участия типов с контрактами сообщений эти ограничения не распространяются.</span><span class="sxs-lookup"><span data-stu-id="895b9-131">Of course, operations that do not involve message contract types are not subject to these restrictions.</span></span>  
  
 <span data-ttu-id="895b9-132">Если тип имеет и контракт сообщения, и контракт данных, при использовании типа в операции во внимание принимается только его контракт сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-132">If a type has both a message contract and a data contract, only its message contract is considered when the type is used in an operation.</span></span>  
  
## <a name="defining-message-contracts"></a><span data-ttu-id="895b9-133">Определение контрактов сообщений</span><span class="sxs-lookup"><span data-stu-id="895b9-133">Defining Message Contracts</span></span>  

 <span data-ttu-id="895b9-134">Чтобы определить контракт сообщения для типа (т. е. определить сопоставление между типом и конвертом SOAP), примените к типу атрибут <xref:System.ServiceModel.MessageContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="895b9-134">To define a message contract for a type (that is, to define the mapping between the type and a SOAP envelope), apply the <xref:System.ServiceModel.MessageContractAttribute> to the type.</span></span> <span data-ttu-id="895b9-135">Затем примените атрибут <xref:System.ServiceModel.MessageHeaderAttribute> к тем членам типа, которые требуется превратить в заголовки SOAP, и примените атрибут <xref:System.ServiceModel.MessageBodyMemberAttribute> к тем членам, которые требуется превратить в части тела сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="895b9-135">Then apply the <xref:System.ServiceModel.MessageHeaderAttribute> to those members of the type you want to make into SOAP headers, and apply the <xref:System.ServiceModel.MessageBodyMemberAttribute> to those members you want to make into parts of the SOAP body of the message.</span></span>  
  
 <span data-ttu-id="895b9-136">Приведенный ниже код представляет собой пример использования контракта сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-136">The following code provides an example of using a message contract.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageHeader] public DateTime transactionDate;  
  [MessageBodyMember] private Account sourceAccount;  
  [MessageBodyMember] private Account targetAccount;  
  [MessageBodyMember] public int amount;  
}  
```  
  
 <span data-ttu-id="895b9-137">При использовании этого типа в качестве параметра операции формируется следующий конверт SOAP:</span><span class="sxs-lookup"><span data-stu-id="895b9-137">When using this type as an operation parameter, the following SOAP envelope is generated:</span></span>  
  
```xml  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <h:operation xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">Deposit</h:operation>  
    <h:transactionDate xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">2012-02-16T16:10:00</h:transactionDate>  
  </s:Header>  
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <BankingTransaction xmlns="http://tempuri.org/">  
      <amount>0</amount>  
      <sourceAccount xsi:nil="true"/>  
      <targetAccount xsi:nil="true"/>  
    </BankingTransaction>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="895b9-138">Обратите внимание, что `operation` и `transactionDate` выглядят как заголовки SOAP, а текст SOAP состоит из элемента-оболочки `BankingTransaction`, содержащего элементы `sourceAccount`, `targetAccount` и `amount`.</span><span class="sxs-lookup"><span data-stu-id="895b9-138">Notice that `operation` and `transactionDate` appear as SOAP headers and the SOAP body consists of a wrapper element `BankingTransaction` containing `sourceAccount`,`targetAccount`, and `amount`.</span></span>  
  
 <span data-ttu-id="895b9-139">Атрибуты <xref:System.ServiceModel.MessageHeaderAttribute> и <xref:System.ServiceModel.MessageBodyMemberAttribute> можно применять ко всем полям, свойствам и событиям, независимо от того, являются они открытыми, закрытыми, защищенными или внутренними.</span><span class="sxs-lookup"><span data-stu-id="895b9-139">You can apply the <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> to all fields, properties, and events, regardless of whether they are public, private, protected, or internal.</span></span>  
  
 <span data-ttu-id="895b9-140">Атрибут <xref:System.ServiceModel.MessageContractAttribute> позволяет указать атрибуты WrapperName и WrapperNamespace, от которых зависит имя элемента-оболочки в тексте сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="895b9-140">The <xref:System.ServiceModel.MessageContractAttribute> allows you to specify the WrapperName and WrapperNamespace attributes which control the name of the wrapper element in the body of the SOAP message.</span></span> <span data-ttu-id="895b9-141">По умолчанию имя типа контракта сообщения используется для оболочки и пространства имен, в котором определен контракт сообщения. `http://tempuri.org/` используется в качестве пространства имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="895b9-141">By default the name of the message contract type is used for the wrapper and the namespace in which the message contract is defined `http://tempuri.org/` is used as the default namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="895b9-142">Атрибуты <xref:System.Runtime.Serialization.KnownTypeAttribute> в контрактах сообщений не учитываются.</span><span class="sxs-lookup"><span data-stu-id="895b9-142"><xref:System.Runtime.Serialization.KnownTypeAttribute> attributes are ignored in message contracts.</span></span> <span data-ttu-id="895b9-143">Если атрибут <xref:System.Runtime.Serialization.KnownTypeAttribute> необходим, поместите его в операцию, в которой используется данный контракт сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-143">If a <xref:System.Runtime.Serialization.KnownTypeAttribute> is required, place it on the operation that is using the message contract in question.</span></span>  
  
## <a name="controlling-header-and-body-part-names-and-namespaces"></a><span data-ttu-id="895b9-144">Управление именами и пространствами имен заголовков и разделов тела</span><span class="sxs-lookup"><span data-stu-id="895b9-144">Controlling Header and Body Part Names and Namespaces</span></span>  

 <span data-ttu-id="895b9-145">В SOAP-представлении контракта сообщения каждый заголовок и раздел тела сообщения сопоставляется с XML-элементом, имеющим имя и пространство имен.</span><span class="sxs-lookup"><span data-stu-id="895b9-145">In the SOAP representation of a message contract, each header and body part maps to an XML element that has a name and a namespace.</span></span>  
  
 <span data-ttu-id="895b9-146">По умолчанию пространство имен совпадает с пространством имен контракта службы, в котором участвует сообщение, а имя определяется именем члена, к которому применены атрибуты <xref:System.ServiceModel.MessageHeaderAttribute> или <xref:System.ServiceModel.MessageBodyMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="895b9-146">By default, the namespace is the same as the namespace of the service contract that the message is participating in, and the name is determined by the member name to which the <xref:System.ServiceModel.MessageHeaderAttribute> or the <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes are applied.</span></span>  
  
 <span data-ttu-id="895b9-147">Изменить значения по умолчанию можно, изменив свойства <xref:System.ServiceModel.MessageContractMemberAttribute.Name%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.MessageContractMemberAttribute.Namespace%2A?displayProperty=nameWithType> (в родительском классе атрибутов <xref:System.ServiceModel.MessageHeaderAttribute> и <xref:System.ServiceModel.MessageBodyMemberAttribute>).</span><span class="sxs-lookup"><span data-stu-id="895b9-147">You can change these defaults by manipulating the <xref:System.ServiceModel.MessageContractMemberAttribute.Name%2A?displayProperty=nameWithType> and <xref:System.ServiceModel.MessageContractMemberAttribute.Namespace%2A?displayProperty=nameWithType> (on the parent class of the <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes).</span></span>  
  
 <span data-ttu-id="895b9-148">Рассмотрим класс в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="895b9-148">Consider the class in the following code example.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageHeader(Namespace="http://schemas.contoso.com/auditing/2005")] public bool IsAudited;  
  [MessageBodyMember(Name="transactionData")] public BankingTransactionData theData;  
}  
```  
  
 <span data-ttu-id="895b9-149">В этом примере заголовок `IsAudited` находится в пространстве имен, заданном в коде, а раздел тела сообщения, представляющий член `theData`, представляется XML-элементом с именем `transactionData`.</span><span class="sxs-lookup"><span data-stu-id="895b9-149">In this example, the `IsAudited` header is in the namespace specified in the code, and the body part that represents the `theData` member is represented by an XML element with the name `transactionData`.</span></span> <span data-ttu-id="895b9-150">Ниже приведен код XML, сформированный для данного контракта сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-150">The following shows the XML generated for this message contract.</span></span>  
  
```xml  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <h:IsAudited xmlns:h="http://schemas.contoso.com/auditing/2005" xmlns="http://schemas.contoso.com/auditing/2005">false</h:IsAudited>  
    <h:operation xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">Deposit</h:operation>  
  </s:Header>  
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <AuditedBankingTransaction xmlns="http://tempuri.org/">  
      <transactionData/>  
    </AuditedBankingTransaction>  
  </s:Body>  
</s:Envelope>  
```  
  
## <a name="controlling-whether-the-soap-body-parts-are-wrapped"></a><span data-ttu-id="895b9-151">Управление заключением разделов тела SOAP-сообщений в оболочку</span><span class="sxs-lookup"><span data-stu-id="895b9-151">Controlling Whether the SOAP Body Parts Are Wrapped</span></span>  

 <span data-ttu-id="895b9-152">По умолчанию разделы тела SOAP-сообщения сериализуются внутри заключенного в оболочку элемента.</span><span class="sxs-lookup"><span data-stu-id="895b9-152">By default, the SOAP body parts are serialized inside a wrapped element.</span></span> <span data-ttu-id="895b9-153">Например, в следующем коде показан элемент-оболочка `HelloGreetingMessage`, сформированный из имени типа <xref:System.ServiceModel.MessageContractAttribute> в контракте сообщения для сообщения `HelloGreetingMessage`.</span><span class="sxs-lookup"><span data-stu-id="895b9-153">For example, the following code shows the `HelloGreetingMessage` wrapper element generated from the name of the <xref:System.ServiceModel.MessageContractAttribute> type in the message contract for the `HelloGreetingMessage` message.</span></span>  
  
[!code-csharp[MessageHeaderAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/messageheaderattribute/cs/services.cs#3)]
[!code-vb[MessageHeaderAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/messageheaderattribute/vb/services.vb#3)]  
  
 <span data-ttu-id="895b9-154">Чтобы подавить элемент-оболочку, присвойте свойству <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="895b9-154">To suppress the wrapper element, set the <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> property to `false`.</span></span> <span data-ttu-id="895b9-155">Для управления именем и пространством имен элемента-оболочки используются свойства <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> и <xref:System.ServiceModel.MessageContractAttribute.WrapperNamespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="895b9-155">To control the name and the namespace of the wrapper element, use the <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> and <xref:System.ServiceModel.MessageContractAttribute.WrapperNamespace%2A> properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="895b9-156">Наличие в сообщениях без оболочки более одного раздела тела противоречит WS-I Basic Profile 1.1 и не рекомендуется при разработке новых контрактов сообщений.</span><span class="sxs-lookup"><span data-stu-id="895b9-156">Having more than one message body part in messages that are not wrapped is not compliant with WS-I Basic Profile 1.1 and is not recommended when designing new message contracts.</span></span> <span data-ttu-id="895b9-157">Тем не менее, в некоторых сценариях взаимодействия может понадобиться иметь несколько разделов тела сообщения без оболочек.</span><span class="sxs-lookup"><span data-stu-id="895b9-157">However, it may be necessary to have more than one unwrapped message body part in certain specific interoperability scenarios.</span></span> <span data-ttu-id="895b9-158">Если планируется передавать в теле сообщения более одного блока данных, рекомендуется использовать режим по умолчанию (с оболочкой).</span><span class="sxs-lookup"><span data-stu-id="895b9-158">If you are going to transmit more than one piece of data in a message body, it is recommended to use the default (wrapped) mode.</span></span> <span data-ttu-id="895b9-159">Наличие в сообщениях без оболочки нескольких заголовков полностью приемлемо.</span><span class="sxs-lookup"><span data-stu-id="895b9-159">Having more than one message header in unwrapped messages is completely acceptable.</span></span>  
  
## <a name="using-custom-types-inside-message-contracts"></a><span data-ttu-id="895b9-160">Использование пользовательских типов внутри контрактов сообщений</span><span class="sxs-lookup"><span data-stu-id="895b9-160">Using Custom Types Inside Message Contracts</span></span>  

 <span data-ttu-id="895b9-161">Каждый отдельный заголовок сообщения и раздел тела сообщения сериализуется (превращается в XML) с помощью модуля сериализации, выбранного для контракта службы, где используется сообщение.</span><span class="sxs-lookup"><span data-stu-id="895b9-161">Each individual message header and message body part is serialized (turned into XML) using the chosen serialization engine for the service contract where the message is used.</span></span> <span data-ttu-id="895b9-162">Модуль сериализации по умолчанию - `XmlFormatter` - способен обработать любой тип, имеющий контракт данных либо явно (т. е. имеющий атрибут <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType>), либо неявно (являющийся типом-примитивом, имеющий атрибут <xref:System.SerializableAttribute?displayProperty=nameWithType> и т. д.).</span><span class="sxs-lookup"><span data-stu-id="895b9-162">The default serialization engine, the `XmlFormatter`, can handle any type that has a data contract, either explicitly (by having the <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType>) or implicitly (by being a primitive type, having the <xref:System.SerializableAttribute?displayProperty=nameWithType>, and so on).</span></span> <span data-ttu-id="895b9-163">Дополнительные сведения см. [в разделе Использование контрактов данных](using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="895b9-163">For more information, see [Using Data Contracts](using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="895b9-164">В приведенном выше примере типы полей `Operation` и `BankingTransactionData` должны иметь контракт данных, а поле `transactionDate` является сериализуемым, потому что тип <xref:System.DateTime> является примитивом (и как таковой имеет неявный контракт данных).</span><span class="sxs-lookup"><span data-stu-id="895b9-164">In the preceding example, the `Operation` and `BankingTransactionData` types must have a data contract, and `transactionDate` is serializable because <xref:System.DateTime> is a primitive (and so has an implicit data contract).</span></span>  
  
 <span data-ttu-id="895b9-165">Тем не менее, можно перейти на другой модуль сериализации - `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="895b9-165">However, it is possible to switch to a different serialization engine, the `XmlSerializer`.</span></span> <span data-ttu-id="895b9-166">В случае такого перехода необходимо убедиться, что все типы, используемые для заголовков и разделов тела сообщений, сериализуются с помощью `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="895b9-166">If you make such a switch, you should ensure that all of the types used for message headers and body parts are serializable using the `XmlSerializer`.</span></span>  
  
## <a name="using-arrays-inside-message-contracts"></a><span data-ttu-id="895b9-167">Использование массивов внутри контрактов сообщений</span><span class="sxs-lookup"><span data-stu-id="895b9-167">Using Arrays Inside Message Contracts</span></span>  

 <span data-ttu-id="895b9-168">В контрактах сообщений можно использовать массивы повторяющихся элементов, причем двумя способами.</span><span class="sxs-lookup"><span data-stu-id="895b9-168">You can use arrays of repeating elements in message contracts in two ways.</span></span>  
  
 <span data-ttu-id="895b9-169">Первый способ - использовать атрибут <xref:System.ServiceModel.MessageHeaderAttribute> или <xref:System.ServiceModel.MessageBodyMemberAttribute> непосредственно в массиве.</span><span class="sxs-lookup"><span data-stu-id="895b9-169">The first is to use a <xref:System.ServiceModel.MessageHeaderAttribute> or a <xref:System.ServiceModel.MessageBodyMemberAttribute> directly on the array.</span></span> <span data-ttu-id="895b9-170">В этом случае весь массив сериализуется как один элемент (т. е. один заголовок или один раздел тела) с несколькими дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="895b9-170">In this case, the entire array is serialized as one element (that is, one header or one body part) with multiple child elements.</span></span> <span data-ttu-id="895b9-171">Рассмотрим класс в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="895b9-171">Consider the class in the following example.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingDepositLog  
{  
  [MessageHeader] public int numRecords;  
  [MessageHeader] public DepositRecord[] records;  
  [MessageHeader] public int branchID;  
}  
```  
  
 <span data-ttu-id="895b9-172">В результате формируются заголовки SOAP-сообщения следующего вида.</span><span class="sxs-lookup"><span data-stu-id="895b9-172">This results in SOAP headers is similar to the following.</span></span>  
  
```xml  
<BankingDepositLog>  
<numRecords>3</numRecords>  
<records>  
  <DepositRecord>Record1</DepositRecord>  
  <DepositRecord>Record2</DepositRecord>  
  <DepositRecord>Record3</DepositRecord>  
</records>  
<branchID>20643</branchID>  
</BankingDepositLog>  
```  
  
 <span data-ttu-id="895b9-173">Альтернативный вариант - использовать атрибут <xref:System.ServiceModel.MessageHeaderArrayAttribute>.</span><span class="sxs-lookup"><span data-stu-id="895b9-173">An alternative to this is to use the <xref:System.ServiceModel.MessageHeaderArrayAttribute>.</span></span> <span data-ttu-id="895b9-174">В этом случае каждый элемент массива сериализуется независимо и, следовательно, каждый элемент массива имеет один заголовок, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="895b9-174">In this case, each array element is serialized independently and so that each array element has one header, similar to the following.</span></span>  
  
```xml  
<numRecords>3</numRecords>  
<records>Record1</records>  
<records>Record2</records>  
<records>Record3</records>  
<branchID>20643</branchID>  
```  
  
 <span data-ttu-id="895b9-175">В качестве имени записей массива по умолчанию используется имя члена, к которому применены атрибуты <xref:System.ServiceModel.MessageHeaderArrayAttribute>.</span><span class="sxs-lookup"><span data-stu-id="895b9-175">The default name for array entries is the name of the member to which the <xref:System.ServiceModel.MessageHeaderArrayAttribute> attributes is applied.</span></span>  
  
 <span data-ttu-id="895b9-176">Атрибут <xref:System.ServiceModel.MessageHeaderArrayAttribute> наследуется от класса <xref:System.ServiceModel.MessageHeaderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="895b9-176">The <xref:System.ServiceModel.MessageHeaderArrayAttribute> attribute inherits from the <xref:System.ServiceModel.MessageHeaderAttribute>.</span></span> <span data-ttu-id="895b9-177">Он имеет тот же набор возможностей, что и атрибуты, не являющиеся массивами; например, можно задать порядок, имя и пространство имен для массива заголовков таким же образом, каким они задаются для отдельного заголовка.</span><span class="sxs-lookup"><span data-stu-id="895b9-177">It has the same set of features as the non-array attributes, for example, it is possible to set the order, name, and namespace for an array of headers in the same way you set it for a single header.</span></span> <span data-ttu-id="895b9-178">При использовании для массива свойство `Order` применяется ко всему массиву.</span><span class="sxs-lookup"><span data-stu-id="895b9-178">When you use the `Order` property on an array, it applies to the entire array.</span></span>  
  
 <span data-ttu-id="895b9-179">Атрибут <xref:System.ServiceModel.MessageHeaderArrayAttribute> можно применять только к массивам, но не к коллекциям.</span><span class="sxs-lookup"><span data-stu-id="895b9-179">You can apply the <xref:System.ServiceModel.MessageHeaderArrayAttribute> only to arrays, not collections.</span></span>  
  
## <a name="using-byte-arrays-in-message-contracts"></a><span data-ttu-id="895b9-180">Использование байтовых массивов в контрактах сообщений</span><span class="sxs-lookup"><span data-stu-id="895b9-180">Using Byte Arrays in Message Contracts</span></span>  

 <span data-ttu-id="895b9-181">При использовании с не являющимися массивами атрибутами (<xref:System.ServiceModel.MessageBodyMemberAttribute> и <xref:System.ServiceModel.MessageHeaderAttribute>) байтовые массивы рассматриваются не как массивы, а как особый тип-примитив, который в итоговом XML-коде представляется данными в кодировке Base64.</span><span class="sxs-lookup"><span data-stu-id="895b9-181">Byte arrays, when used with the non-array attributes (<xref:System.ServiceModel.MessageBodyMemberAttribute> and <xref:System.ServiceModel.MessageHeaderAttribute>), are not treated as arrays but as a special primitive type represented as Base64-encoded data in the resulting XML.</span></span>  
  
 <span data-ttu-id="895b9-182">При использовании байтовых массивов с атрибутом-массивом <xref:System.ServiceModel.MessageHeaderArrayAttribute> результаты зависят от используемого сериализатора.</span><span class="sxs-lookup"><span data-stu-id="895b9-182">When you use byte arrays with the array attribute <xref:System.ServiceModel.MessageHeaderArrayAttribute>, the results depend on the serializer in use.</span></span> <span data-ttu-id="895b9-183">При использовании сериализатора по умолчанию массив представляется в виде отдельных записей для каждого байта.</span><span class="sxs-lookup"><span data-stu-id="895b9-183">With the default serializer, the array is represented as an individual entry for each byte.</span></span> <span data-ttu-id="895b9-184">Если же выбран сериализатор `XmlSerializer` (с помощью атрибута <xref:System.ServiceModel.XmlSerializerFormatAttribute> в контракте службы), байтовые массивы рассматриваются как данные в кодировке Base64 независимо от того, какие атрибуты используются - массивы или нет.</span><span class="sxs-lookup"><span data-stu-id="895b9-184">However, when the `XmlSerializer` is selected, (using the <xref:System.ServiceModel.XmlSerializerFormatAttribute> on the service contract), byte arrays are treated as Base64 data regardless of whether the array or non-array attributes are used.</span></span>  
  
## <a name="signing-and-encrypting-parts-of-the-message"></a><span data-ttu-id="895b9-185">Подписывание и шифрование частей сообщения</span><span class="sxs-lookup"><span data-stu-id="895b9-185">Signing and Encrypting Parts of the Message</span></span>  

 <span data-ttu-id="895b9-186">В контракте сообщения может быть указано, следует ли снабжать заголовки и/или тело сообщения цифровыми подписями и шифровать.</span><span class="sxs-lookup"><span data-stu-id="895b9-186">A message contract can indicate whether the headers and/or body of the message should be digitally signed and encrypted.</span></span>  
  
 <span data-ttu-id="895b9-187">Это можно сделать, задав свойство <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A?displayProperty=nameWithType> атрибутов <xref:System.ServiceModel.MessageHeaderAttribute> и <xref:System.ServiceModel.MessageBodyMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="895b9-187">This is done by setting the <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A?displayProperty=nameWithType> property on the <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes.</span></span> <span data-ttu-id="895b9-188">Это свойство является перечислением типа <xref:System.Net.Security.ProtectionLevel?displayProperty=nameWithType> и может принимать значения <xref:System.Net.Security.ProtectionLevel.None> (без шифрования или подписи), <xref:System.Net.Security.ProtectionLevel.Sign> (только цифровая подпись) или <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> (и шифрование, и цифровая подпись).</span><span class="sxs-lookup"><span data-stu-id="895b9-188">The property is an enumeration of the <xref:System.Net.Security.ProtectionLevel?displayProperty=nameWithType> type and can be set to <xref:System.Net.Security.ProtectionLevel.None> (no encryption or signature), <xref:System.Net.Security.ProtectionLevel.Sign> (digital signature only), or <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> (both encryption and a digital signature).</span></span> <span data-ttu-id="895b9-189">Значение по умолчанию — <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span><span class="sxs-lookup"><span data-stu-id="895b9-189">The default is <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
 <span data-ttu-id="895b9-190">Чтобы эти возможности безопасности работали, необходимо надлежащим образом настроить привязку и расширения функциональности.</span><span class="sxs-lookup"><span data-stu-id="895b9-190">For these security features to work, you must properly configure the binding and behaviors.</span></span> <span data-ttu-id="895b9-191">При использовании этих возможностей безопасности без надлежащей настройки (например, при попытке подписать сообщение без предоставления учетных данных) во время проверки будет вызвано исключение.</span><span class="sxs-lookup"><span data-stu-id="895b9-191">If you use these security features without the proper configuration (for example, attempting to sign a message without supplying your credentials), an exception is thrown at validation time.</span></span>  
  
 <span data-ttu-id="895b9-192">Для заголовков сообщений уровень защиты определяется отдельно для каждого заголовка.</span><span class="sxs-lookup"><span data-stu-id="895b9-192">For message headers, the protection level is determined individually for each header.</span></span>  
  
 <span data-ttu-id="895b9-193">Для разделов тела сообщений уровень защиты можно понимать как «минимальный уровень защиты».</span><span class="sxs-lookup"><span data-stu-id="895b9-193">For message body parts, the protection level can be thought of as the "minimum protection level."</span></span> <span data-ttu-id="895b9-194">Тело имеет только один уровень защиты, независимо от количества разделов тела.</span><span class="sxs-lookup"><span data-stu-id="895b9-194">The body has only one protection level, regardless of the number of body parts.</span></span> <span data-ttu-id="895b9-195">Уровень защиты текста определяется наивысшим из значений свойства <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A> всех разделов текста.</span><span class="sxs-lookup"><span data-stu-id="895b9-195">The protection level of the body is determined by the highest <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A> property setting of all the body parts.</span></span> <span data-ttu-id="895b9-196">Тем не менее для каждого раздела тела сообщения следует задавать фактически необходимый минимальный уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="895b9-196">However, you should set the protection level of each body part to the actual minimum protection level required.</span></span>  
  
 <span data-ttu-id="895b9-197">Рассмотрим класс в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="895b9-197">Consider the class in the following code example.</span></span>  
  
```csharp  
[MessageContract]  
public class PatientRecord  
{  
   [MessageHeader(ProtectionLevel=None)] public int recordID;  
   [MessageHeader(ProtectionLevel=Sign)] public string patientName;  
   [MessageHeader(ProtectionLevel=EncryptAndSign)] public string SSN;  
   [MessageBodyMember(ProtectionLevel=None)] public string comments;  
   [MessageBodyMember(ProtectionLevel=Sign)] public string diagnosis;  
   [MessageBodyMember(ProtectionLevel=EncryptAndSign)] public string medicalHistory;  
}  
```  
  
 <span data-ttu-id="895b9-198">В этом примере заголовок `recordID` не защищается, заголовок `patientName``signed`, а заголовок `SSN` шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="895b9-198">In this example, the `recordID` header is not protected, `patientName` is `signed`, and `SSN` is encrypted and signed.</span></span> <span data-ttu-id="895b9-199">Как минимум к одному разделу тела - `medicalHistory` - применено свойство <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>; следовательно, все тело сообщения шифруется и подписывается, хотя для разделов комментариев и диагноза заданы более низкие уровни защиты.</span><span class="sxs-lookup"><span data-stu-id="895b9-199">At least one body part, `medicalHistory`, has <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> applied, and thus the entire message body is encrypted and signed, even though the comments and diagnosis body parts specify lower protection levels.</span></span>  
  
## <a name="soap-action"></a><span data-ttu-id="895b9-200">Свойство Action протокола SOAP</span><span class="sxs-lookup"><span data-stu-id="895b9-200">SOAP Action</span></span>  

 <span data-ttu-id="895b9-201">В протоколе SOAP и связанных с ним стандартах веб-служб определено свойство с именем `Action`, которое может присутствовать для каждого оправляемого SOAP-сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-201">SOAP and related Web services standards define a property called `Action` that can be present for every SOAP message sent.</span></span> <span data-ttu-id="895b9-202">Значение этого свойства определяется свойствами <xref:System.ServiceModel.OperationContractAttribute.Action%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A?displayProperty=nameWithType> операции.</span><span class="sxs-lookup"><span data-stu-id="895b9-202">The operation's <xref:System.ServiceModel.OperationContractAttribute.Action%2A?displayProperty=nameWithType> and <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A?displayProperty=nameWithType> properties control the value of this property.</span></span>  
  
## <a name="soap-header-attributes"></a><span data-ttu-id="895b9-203">Атрибуты заголовка по протоколу SOAP</span><span class="sxs-lookup"><span data-stu-id="895b9-203">SOAP Header Attributes</span></span>  

 <span data-ttu-id="895b9-204">В стандарте протокола SOAP определены следующие атрибуты, которые могут присутствовать в заголовке:</span><span class="sxs-lookup"><span data-stu-id="895b9-204">The SOAP standard defines the following attributes that may exist on a header:</span></span>  
  
- <span data-ttu-id="895b9-205">`Actor/Role` (`Actor` в SOAP 1.1, `Role` в SOAP 1.2)</span><span class="sxs-lookup"><span data-stu-id="895b9-205">`Actor/Role` (`Actor` in SOAP 1.1, `Role` in SOAP 1.2)</span></span>  
  
- `MustUnderstand`  
  
- `Relay`  
  
 <span data-ttu-id="895b9-206">Атрибут `Actor` или `Role` задает универсальный код ресурса (URI) узла, для которого предназначен данный заголовок.</span><span class="sxs-lookup"><span data-stu-id="895b9-206">The `Actor` or `Role` attribute specifies the Uniform Resource Identifier (URI) of the node for which a given header is intended.</span></span> <span data-ttu-id="895b9-207">Атрибут `MustUnderstand` указывает, должен ли обрабатывающий заголовок узел понимать его.</span><span class="sxs-lookup"><span data-stu-id="895b9-207">The `MustUnderstand` attribute specifies whether the node processing the header must understand it.</span></span> <span data-ttu-id="895b9-208">Атрибут `Relay` указывает, надо ли передавать заголовок на нижележащие узлы.</span><span class="sxs-lookup"><span data-stu-id="895b9-208">The `Relay` attribute specifies whether the header is to be relayed to downstream nodes.</span></span> <span data-ttu-id="895b9-209">WCF не выполняет обработку этих атрибутов для входящих сообщений, за исключением `MustUnderstand` атрибута, как указано в подразделе "Управление версиями контракта сообщений" Далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="895b9-209">WCF does not perform any processing of these attributes on incoming messages, except for the `MustUnderstand` attribute, as specified in the "Message Contract Versioning" section later in this topic.</span></span> <span data-ttu-id="895b9-210">Тем не менее, при необходимости эти атрибуты можно считывать и записывать, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="895b9-210">However, it allows you to read and write these attributes as necessary, as in the following description.</span></span>  
  
 <span data-ttu-id="895b9-211">При отправке сообщения эти атрибуты по умолчанию не выдаются.</span><span class="sxs-lookup"><span data-stu-id="895b9-211">When sending a message, these attributes are not emitted by default.</span></span> <span data-ttu-id="895b9-212">Это поведение можно изменить двумя способами.</span><span class="sxs-lookup"><span data-stu-id="895b9-212">You can change this in two ways.</span></span> <span data-ttu-id="895b9-213">Во-первых, можно статически присвоить атрибутам любые требуемые значения, изменяя свойства <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.MessageHeaderAttribute.MustUnderstand%2A?displayProperty=nameWithType> и <xref:System.ServiceModel.MessageHeaderAttribute.Relay%2A?displayProperty=nameWithType>, как показано в предыдущем примере кода.</span><span class="sxs-lookup"><span data-stu-id="895b9-213">First, you may statically set the attributes to any desired values by changing the <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.MessageHeaderAttribute.MustUnderstand%2A?displayProperty=nameWithType>, and <xref:System.ServiceModel.MessageHeaderAttribute.Relay%2A?displayProperty=nameWithType> properties, as shown in the following code example.</span></span> <span data-ttu-id="895b9-214">(Обратите внимание, что свойства `Role` здесь нет; задание свойства <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A> порождает атрибут `Role` при использовании протокола SOAP 1.2).</span><span class="sxs-lookup"><span data-stu-id="895b9-214">(Note that there is no `Role` property; setting the <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A> property emits the `Role` attribute if you are using SOAP 1.2).</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader(Actor="http://auditingservice.contoso.com", MustUnderstand=true)] public bool IsAudited;  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public BankingTransactionData theData;  
}  
```  
  
 <span data-ttu-id="895b9-215">Второй способ управлять этими атрибутами - динамически посредством кода.</span><span class="sxs-lookup"><span data-stu-id="895b9-215">The second way to control these attributes is dynamically, through code.</span></span> <span data-ttu-id="895b9-216">Это можно делать, заключая требуемый тип заголовка в тип <xref:System.ServiceModel.MessageHeader%601> (не путайте этот тип с неуниверсальной версией) и используя тип вместе с атрибутом <xref:System.ServiceModel.MessageHeaderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="895b9-216">You can achieve this by wrapping the desired header type in the <xref:System.ServiceModel.MessageHeader%601> type (be sure not to confuse this type with the non-generic version) and by using the type together with the <xref:System.ServiceModel.MessageHeaderAttribute>.</span></span> <span data-ttu-id="895b9-217">Затем можно использовать свойства класса <xref:System.ServiceModel.MessageHeader%601> для задания атрибутов протокола SOAP, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="895b9-217">Then, you can use properties on the <xref:System.ServiceModel.MessageHeader%601> to set the SOAP attributes, as shown in the following code example.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public MessageHeader<bool> IsAudited;  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public BankingTransactionData theData;  
}  
// application code:  
BankingTransaction bt = new BankingTransaction();  
bt.IsAudited = new MessageHeader<bool>();  
bt.IsAudited.Content = false; // Set IsAudited header value to "false"  
bt.IsAudited.Actor="http://auditingservice.contoso.com";  
bt.IsAudited.MustUnderstand=true;  
```  
  
 <span data-ttu-id="895b9-218">Если используются и динамический, и статический механизмы управления, статические параметры используются по умолчанию, однако могут позднее быть переопределены с помощью динамического механизма, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="895b9-218">If you use both the dynamic and the static control mechanisms, the static settings are used as a default but can later be overridden by using the dynamic mechanism, as shown in the following code.</span></span>  
  
```csharp  
[MessageHeader(MustUnderstand=true)] public MessageHeader<Person> documentApprover;  
// later on in the code:  
BankingTransaction bt = new BankingTransaction();  
bt.documentApprover = new MessageHeader<Person>();  
bt.documentApprover.MustUnderstand = false; // override the static default of 'true'  
```  
  
 <span data-ttu-id="895b9-219">Допускается создание повторяющихся заголовков с динамическим управлением атрибутами, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="895b9-219">Creating repeated headers with dynamic attribute control is allowed, as shown in the following code.</span></span>  
  
```csharp  
[MessageHeaderArray] public MessageHeader<Person> documentApprovers[];  
```  
  
 <span data-ttu-id="895b9-220">На стороне получения чтение этих атрибутов SOAP возможно только при использовании класса <xref:System.ServiceModel.MessageHeader%601> для заголовка в типе.</span><span class="sxs-lookup"><span data-stu-id="895b9-220">On the receiving side, reading these SOAP attributes can only be done if the <xref:System.ServiceModel.MessageHeader%601> class is used for the header in the type.</span></span> <span data-ttu-id="895b9-221">Для определения значений атрибутов полученного сообщения рассмотрите свойства `Actor`, `Relay` или `MustUnderstand` заголовка типа <xref:System.ServiceModel.MessageHeader%601>.</span><span class="sxs-lookup"><span data-stu-id="895b9-221">Examine the `Actor`, `Relay`, or `MustUnderstand` properties of a header of the <xref:System.ServiceModel.MessageHeader%601> type to discover the attribute settings on the received message.</span></span>  
  
 <span data-ttu-id="895b9-222">При получении сообщения и затем отправке его обратно круговой путь совершают только значения атрибутов SOAP для заголовков типа <xref:System.ServiceModel.MessageHeader%601>.</span><span class="sxs-lookup"><span data-stu-id="895b9-222">When a message is received and then sent back, the SOAP attribute settings only go round-trip for headers of the <xref:System.ServiceModel.MessageHeader%601> type.</span></span>  
  
## <a name="order-of-soap-body-parts"></a><span data-ttu-id="895b9-223">Порядок разделов тела SOAP-сообщения</span><span class="sxs-lookup"><span data-stu-id="895b9-223">Order of SOAP Body Parts</span></span>  

 <span data-ttu-id="895b9-224">В некоторых случаях может потребоваться управлять порядком разделов тела сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-224">In some circumstances, you may need to control the order of the body parts.</span></span> <span data-ttu-id="895b9-225">По умолчанию порядок элементов текста сообщения алфавитный, однако его можно изменить с помощью свойства <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="895b9-225">The order of the body elements is alphabetical by default, but can be controlled by the <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="895b9-226">Это свойство имеет ту же семантику, что и свойство <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A?displayProperty=nameWithType>, за исключением поведения в сценариях наследования (в контрактах сообщений элементы тела сообщения базовых типов не сортируются перед элементами тела сообщения производных типов).</span><span class="sxs-lookup"><span data-stu-id="895b9-226">This property has the same semantics as the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A?displayProperty=nameWithType> property, except for the behavior in inheritance scenarios (in message contracts, base type body members are not sorted before the derived type body members).</span></span> <span data-ttu-id="895b9-227">Дополнительные сведения см. в разделе [порядок элементов данных](data-member-order.md).</span><span class="sxs-lookup"><span data-stu-id="895b9-227">For more information, see [Data Member Order](data-member-order.md).</span></span>  
  
 <span data-ttu-id="895b9-228">В следующем примере элемент `amount` в обычном случае был бы первым, поскольку он идет первым по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="895b9-228">In the following example, `amount` would normally come first because it is first alphabetically.</span></span> <span data-ttu-id="895b9-229">Однако в данном случае свойство <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A> помещает его на третью позицию.</span><span class="sxs-lookup"><span data-stu-id="895b9-229">However, the <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A> property puts it into the third position.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember(Order=1)] public Account sourceAccount;  
  [MessageBodyMember(Order=2)] public Account targetAccount;  
  [MessageBodyMember(Order=3)] public int amount;  
}  
```  
  
## <a name="message-contract-versioning"></a><span data-ttu-id="895b9-230">Управление версиями контракта сообщения</span><span class="sxs-lookup"><span data-stu-id="895b9-230">Message Contract Versioning</span></span>  

 <span data-ttu-id="895b9-231">Иногда контракты сообщений требуется изменять.</span><span class="sxs-lookup"><span data-stu-id="895b9-231">Occasionally, you may need to change message contracts.</span></span> <span data-ttu-id="895b9-232">Например, новая версия приложения может добавлять в сообщение дополнительный заголовок.</span><span class="sxs-lookup"><span data-stu-id="895b9-232">For example, a new version of your application may add an extra header to a message.</span></span> <span data-ttu-id="895b9-233">Затем при отправке сообщений от новой версии к старой системе приходится иметь дело с дополнительным заголовком, равно как и с недостающим заголовком при отправке сообщений в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="895b9-233">Then, when sending from the new version to the old, the system must deal with an extra header, as well as a missing header when going in the other direction.</span></span>  
  
 <span data-ttu-id="895b9-234">К управлению версиями заголовков применяются следующие правила.</span><span class="sxs-lookup"><span data-stu-id="895b9-234">The following rules apply for versioning headers:</span></span>  
  
- <span data-ttu-id="895b9-235">WCF не выполняет объект для отсутствующих заголовков — соответствующие члены остаются в значениях по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="895b9-235">WCF does not object to the missing headers—the corresponding members are left at their default values.</span></span>  
  
- <span data-ttu-id="895b9-236">WCF также игнорирует непредвиденные дополнительные заголовки.</span><span class="sxs-lookup"><span data-stu-id="895b9-236">WCF also ignores unexpected extra headers.</span></span> <span data-ttu-id="895b9-237">Единственное исключение из этого правила - когда дополнительный заголовок входящего SOAP-сообщения имеет атрибут `MustUnderstand` со значением `true`. В этом случае вызывается исключение, поскольку не удается обработать заголовок, который должен быть понят.</span><span class="sxs-lookup"><span data-stu-id="895b9-237">The one exception to this rule is if the extra header has a `MustUnderstand` attribute set to `true` in the incoming SOAP message—in this case, an exception is thrown because a header that must be understood cannot be processed.</span></span>  
  
 <span data-ttu-id="895b9-238">Аналогичные правила управления версиями применяются к телам сообщений - и недостающие, и дополнительные разделы тела сообщения не учитываются.</span><span class="sxs-lookup"><span data-stu-id="895b9-238">Message bodies have similar versioning rules—both missing and additional message body parts are ignored.</span></span>  
  
## <a name="inheritance-considerations"></a><span data-ttu-id="895b9-239">Замечания о наследовании</span><span class="sxs-lookup"><span data-stu-id="895b9-239">Inheritance Considerations</span></span>  

 <span data-ttu-id="895b9-240">Тип с контрактом сообщения может наследовать от другого типа при условии, что базовый тип также имеет контракт сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-240">A message contract type can inherit from another type, as long as the base type also has a message contract.</span></span>  
  
 <span data-ttu-id="895b9-241">При создании сообщения или доступе к сообщению с использованием типа с контрактом сообщения, наследующего от других типов с контрактами сообщений, применяются следующие правила.</span><span class="sxs-lookup"><span data-stu-id="895b9-241">When creating or accessing a message using a message contract type that inherits from other message contract types, the following rules apply:</span></span>  
  
- <span data-ttu-id="895b9-242">Все заголовки сообщения в иерархии наследования собираются вместе и образуют полный набор заголовков для сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-242">All of the message headers in the inheritance hierarchy are collected together to form the full set of headers for the message.</span></span>  
  
- <span data-ttu-id="895b9-243">Все разделы тела сообщения в иерархии наследования собираются вместе и образуют полное тело сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-243">All of the message body parts in the inheritance hierarchy are collected together to form the full message body.</span></span> <span data-ttu-id="895b9-244">Разделы текста сообщения упорядочиваются согласно обычным правилам (по свойству <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType>, а затем по алфавиту), независимо от их места в иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="895b9-244">The body parts are ordered according to the usual ordering rules (by <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType> property and then alphabetical), with no relevance to their place in the inheritance hierarchy.</span></span> <span data-ttu-id="895b9-245">Использовать наследование контрактов сообщения в случаях, где разделы тела сообщения имеются на нескольких уровнях дерева наследования, крайне нежелательно.</span><span class="sxs-lookup"><span data-stu-id="895b9-245">Using message contract inheritance where message body parts occur at multiple levels of the inheritance tree is strongly discouraged.</span></span> <span data-ttu-id="895b9-246">Если базовый класс и производный класс определяют заголовок или раздел тела сообщения с одинаковым именем, для хранения значения этого заголовка или раздела тела используется член «самого базового» класса.</span><span class="sxs-lookup"><span data-stu-id="895b9-246">If a base class and a derived class define a header or a body part with the same name, the member from the base-most class is used to store the value of that header or body part.</span></span>  
  
 <span data-ttu-id="895b9-247">Рассмотрим классы в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="895b9-247">Consider the classes in the following code example.</span></span>  
  
```csharp  
[MessageContract]  
public class PersonRecord  
{  
  [MessageHeader(Name="ID")] public int personID;  
  [MessageBodyMember] public string patientName;  
}  
  
[MessageContract]  
public class PatientRecord : PersonRecord  
{  
  [MessageHeader(Name="ID")] public int patientID;  
  [MessageBodyMember] public string diagnosis;  
}  
```  
  
 <span data-ttu-id="895b9-248">Класс `PatientRecord` описывает сообщение с одним заголовком с именем `ID`.</span><span class="sxs-lookup"><span data-stu-id="895b9-248">The `PatientRecord` class describes a message with one header called `ID`.</span></span> <span data-ttu-id="895b9-249">Этот заголовок соответствует члену `personID`, а не члену `patientID`, поскольку выбирается самый базовый член.</span><span class="sxs-lookup"><span data-stu-id="895b9-249">The header corresponds to the `personID` and not the `patientID` member, because the base-most member is chosen.</span></span> <span data-ttu-id="895b9-250">Следовательно, поле `patientID` в этом случае бесполезно.</span><span class="sxs-lookup"><span data-stu-id="895b9-250">Thus, the `patientID` field is useless in this case.</span></span> <span data-ttu-id="895b9-251">Тело сообщения содержит элемент `diagnosis`, за которым следует элемент `patientName` (алфавитный порядок).</span><span class="sxs-lookup"><span data-stu-id="895b9-251">The body of the message contains the `diagnosis` element followed by the `patientName` element, because that is the alphabetical order.</span></span> <span data-ttu-id="895b9-252">Обратите внимание, что в этом примере показана крайне нежелательная схема: и в базовом, и в производном контракте сообщения имеются разделы тела сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-252">Notice that the example shows a pattern that is strongly discouraged: both the base and the derived message contracts have message body parts.</span></span>  
  
## <a name="wsdl-considerations"></a><span data-ttu-id="895b9-253">Замечания о WSDL</span><span class="sxs-lookup"><span data-stu-id="895b9-253">WSDL Considerations</span></span>  

 <span data-ttu-id="895b9-254">При создании контракта на языке WSDL из службы, в которой используются контракты сообщений, важно помнить, что в полученном WSDL-коде отражаются не все возможности контракта сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-254">When generating a Web Services Description Language (WSDL) contract from a service that uses message contracts, it is important to remember that not all message contract features are reflected in the resulting WSDL.</span></span> <span data-ttu-id="895b9-255">Учтите следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="895b9-255">Consider the following points:</span></span>  
  
- <span data-ttu-id="895b9-256">На языке WSDL нельзя выразить понятие массива заголовков.</span><span class="sxs-lookup"><span data-stu-id="895b9-256">WSDL cannot express the concept of an array of headers.</span></span> <span data-ttu-id="895b9-257">При создании сообщений с массивом заголовков с использованием атрибута <xref:System.ServiceModel.MessageHeaderArrayAttribute> в полученном WSDL-коде вместо массива отражается только один заголовок.</span><span class="sxs-lookup"><span data-stu-id="895b9-257">When creating messages with an array of headers using the <xref:System.ServiceModel.MessageHeaderArrayAttribute>, the resulting WSDL reflects only one header instead of the array.</span></span>  
  
- <span data-ttu-id="895b9-258">Полученный WSDL-документ может не отражать некоторую информацию об уровне защиты.</span><span class="sxs-lookup"><span data-stu-id="895b9-258">The resulting WSDL document may not reflect some protection-level information.</span></span>  
  
- <span data-ttu-id="895b9-259">Имя типа сообщения, сформированного в WSDL-коде, совпадает с именем класса типа контракта сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-259">The message type generated in the WSDL has the same name as the class name of the message contract type.</span></span>  
  
- <span data-ttu-id="895b9-260">При использовании в нескольких операциях одного и того же контракта сообщения в WSDL-документе формируется несколько типов сообщений.</span><span class="sxs-lookup"><span data-stu-id="895b9-260">When using the same message contract in multiple operations, multiple message types are generated in the WSDL document.</span></span> <span data-ttu-id="895b9-261">Имена делаются уникальными путем добавления номеров "2", "3" и т. д. для использования в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="895b9-261">The names are made unique by adding the numbers "2", "3", and so on, for subsequent uses.</span></span> <span data-ttu-id="895b9-262">При обратном импорте WSDL-кода создается несколько типов с контрактами сообщений, идентичных за исключением имен.</span><span class="sxs-lookup"><span data-stu-id="895b9-262">When importing back the WSDL, multiple message contract types are created and are identical except for their names.</span></span>  
  
## <a name="soap-encoding-considerations"></a><span data-ttu-id="895b9-263">Замечания о кодировании SOAP</span><span class="sxs-lookup"><span data-stu-id="895b9-263">SOAP Encoding Considerations</span></span>  

 <span data-ttu-id="895b9-264">WCF позволяет использовать устаревший стиль кодирования SOAP XML, однако его использование не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="895b9-264">WCF allows you to use the legacy SOAP encoding style of XML, however, its use is not recommended.</span></span> <span data-ttu-id="895b9-265">При использовании этого стиля (путем присвоения значения `Use` свойству `Encoded` атрибута <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>, примененного к контракту службы) следует принять во внимание также следующее.</span><span class="sxs-lookup"><span data-stu-id="895b9-265">When using this style (by setting the `Use` property to `Encoded` on the <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType> applied to the service contract), the following additional considerations apply:</span></span>  
  
- <span data-ttu-id="895b9-266">Заголовки сообщений не поддерживаются; это значит, что атрибут <xref:System.ServiceModel.MessageHeaderAttribute> и атрибут-массив <xref:System.ServiceModel.MessageHeaderArrayAttribute> несовместимы с кодированием SOAP.</span><span class="sxs-lookup"><span data-stu-id="895b9-266">The message headers are not supported; this means that the attribute <xref:System.ServiceModel.MessageHeaderAttribute> and the array attribute <xref:System.ServiceModel.MessageHeaderArrayAttribute> are incompatible with SOAP encoding.</span></span>  
  
- <span data-ttu-id="895b9-267">Если контракт сообщения не заключен в оболочку, т. е. если свойство <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> имеет значение `false`, контракт сообщения может иметь только один раздел тела сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-267">If the message contract is not wrapped, that is, if the property <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> is set to `false`, the message contract can have only one body part.</span></span>  
  
- <span data-ttu-id="895b9-268">Имя элемента-оболочки для контракта сообщения запроса должно совпадать с именем операции.</span><span class="sxs-lookup"><span data-stu-id="895b9-268">The name of the wrapper element for the request message contract must match the operation name.</span></span> <span data-ttu-id="895b9-269">Для этого используется свойство `WrapperName` контракта сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-269">Use the `WrapperName` property of the message contract for this.</span></span>  
  
- <span data-ttu-id="895b9-270">Имя элемента-оболочки для контракта ответного сообщения должно представлять собой имя операции, снабженное суффиксом "Response".</span><span class="sxs-lookup"><span data-stu-id="895b9-270">The name of the wrapper element for the response message contract must be the same as the name of the operation suffixed by 'Response'.</span></span> <span data-ttu-id="895b9-271">Для этого используется свойство <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> контракта сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-271">Use the <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> property of the message contract for this.</span></span>  
  
- <span data-ttu-id="895b9-272">Кодирование SOAP сохраняет ссылки на объекты.</span><span class="sxs-lookup"><span data-stu-id="895b9-272">SOAP encoding preserves object references.</span></span> <span data-ttu-id="895b9-273">Например, рассмотрим следующий код.</span><span class="sxs-lookup"><span data-stu-id="895b9-273">For example, consider the following code.</span></span>  
  
    ```csharp  
    [MessageContract(WrapperName="updateChangeRecord")]  
    public class ChangeRecordRequest  
    {  
      [MessageBodyMember] Person changedBy;  
      [MessageBodyMember] Person changedFrom;  
      [MessageBodyMember] Person changedTo;  
    }  
  
    [MessageContract(WrapperName="updateChangeRecordResponse")]  
    public class ChangeRecordResponse  
    {  
      [MessageBodyMember] Person changedBy;  
      [MessageBodyMember] Person changedFrom;  
      [MessageBodyMember] Person changedTo;  
    }  
  
    // application code:  
    ChangeRecordRequest cr = new ChangeRecordRequest();  
    Person p = new Person("John Doe");  
    cr.changedBy=p;  
    cr.changedFrom=p;  
    cr.changedTo=p;  
    ```  
  
 <span data-ttu-id="895b9-274">После сериализации сообщения с использованием кодирования SOAP элементы `changedFrom` и `changedTo` не содержат собственных копий `p`, а вместо этого указывают на копию внутри элемента `changedBy`.</span><span class="sxs-lookup"><span data-stu-id="895b9-274">After serializing the message using SOAP encoding, `changedFrom` and `changedTo` do not contain their own copies of `p`, but instead point to the copy inside the `changedBy` element.</span></span>  
  
## <a name="performance-considerations"></a><span data-ttu-id="895b9-275">Вопросы производительности</span><span class="sxs-lookup"><span data-stu-id="895b9-275">Performance Considerations</span></span>  

 <span data-ttu-id="895b9-276">Каждый заголовок сообщения и раздел тела сообщения сериализуется независимо от других.</span><span class="sxs-lookup"><span data-stu-id="895b9-276">Every message header and message body part is serialized independently of the others.</span></span> <span data-ttu-id="895b9-277">Следовательно, одни те же пространства имен могут повторно объявляться для каждого заголовка и раздела тела.</span><span class="sxs-lookup"><span data-stu-id="895b9-277">Therefore, the same namespaces can be declared again for each header and body part.</span></span> <span data-ttu-id="895b9-278">Для улучшения производительности, особенно в части размера сообщения на линии связи, множественные заголовки и разделы тела сообщения следует объединять в один заголовок или раздел тела.</span><span class="sxs-lookup"><span data-stu-id="895b9-278">To improve performance, especially in terms of the size of the message on the wire, consolidate multiple headers and body parts into a single header or body part.</span></span> <span data-ttu-id="895b9-279">Например, вместо следующего кода</span><span class="sxs-lookup"><span data-stu-id="895b9-279">For example, instead of the following code:</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public Account sourceAccount;  
  [MessageBodyMember] public Account targetAccount;  
  [MessageBodyMember] public int amount;  
}  
```  
  
 <span data-ttu-id="895b9-280">используйте такой код:</span><span class="sxs-lookup"><span data-stu-id="895b9-280">Use this code.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public OperationDetails details;  
}  
  
[DataContract]  
public class OperationDetails  
{  
  [DataMember] public Account sourceAccount;  
  [DataMember] public Account targetAccount;  
  [DataMember] public int amount;  
}  
```  
  
### <a name="event-based-asynchronous-and-message-contracts"></a><span data-ttu-id="895b9-281">Асинхронная модель на основе событий и контракты сообщений</span><span class="sxs-lookup"><span data-stu-id="895b9-281">Event-based Asynchronous and Message Contracts</span></span>  

 <span data-ttu-id="895b9-282">Согласно правилам разработки для асинхронной модели на основе событий, если возвращается несколько значений, одно значение возвращается как свойство `Result`, а остальные возвращаются как свойства объекта <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="895b9-282">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="895b9-283">Одним из результатов этого является то, что если клиент импортирует метаданные с использованием параметров асинхронных команд на основе событий и операция возвращает более одного значения, объект <xref:System.EventArgs> по умолчанию возвращает одно значение как свойство `Result`, а остальные являются свойствами объекта <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="895b9-283">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.</span></span>  
  
 <span data-ttu-id="895b9-284">Если требуется получать объект сообщения как свойство `Result`, чтобы возвращаемые значения были свойствами этого объекта, используйте параметр команды `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="895b9-284">If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="895b9-285">При этом формируется сигнатура, которая возвращает ответное сообщение как свойство `Result` объекта <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="895b9-285">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="895b9-286">Все внутренние возвращаемые значения тогда будут свойствами объекта ответного сообщения.</span><span class="sxs-lookup"><span data-stu-id="895b9-286">All internal return values are then properties of the response message object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="895b9-287">См. также</span><span class="sxs-lookup"><span data-stu-id="895b9-287">See also</span></span>

- [<span data-ttu-id="895b9-288">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="895b9-288">Using Data Contracts</span></span>](using-data-contracts.md)
- [<span data-ttu-id="895b9-289">Проектирование и реализация служб</span><span class="sxs-lookup"><span data-stu-id="895b9-289">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)
