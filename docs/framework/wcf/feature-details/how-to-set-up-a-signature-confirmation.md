---
title: Практическое руководство. Настройка подтверждения сигнатуры
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signature confirmation
- WCF, security
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
ms.openlocfilehash: 9423922753efee7aac32e430f97307c715e43464
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84586927"
---
# <a name="how-to-set-up-a-signature-confirmation"></a><span data-ttu-id="c1e50-102">Практическое руководство. Настройка подтверждения сигнатуры</span><span class="sxs-lookup"><span data-stu-id="c1e50-102">How to: Set Up a Signature Confirmation</span></span>

<span data-ttu-id="c1e50-103">*Подтверждение сигнатуры* — это механизм для инициатора сообщений, гарантирующий, что полученный ответ был создан в ответ на исходное сообщение отправителя.</span><span class="sxs-lookup"><span data-stu-id="c1e50-103">*Signature confirmation* is a mechanism for a message initiator to ensure that a received reply was generated in response to the sender's original message.</span></span> <span data-ttu-id="c1e50-104">Подтверждение подписи определено в спецификации WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="c1e50-104">Signature confirmation is defined in the WS-Security 1.1 specification.</span></span> <span data-ttu-id="c1e50-105">Если конечная точка поддерживает WS-Security 1.0, использовать подтверждение подписи нельзя.</span><span class="sxs-lookup"><span data-stu-id="c1e50-105">If an endpoint supports WS-Security 1.0, you cannot use signature confirmation.</span></span>

<span data-ttu-id="c1e50-106">В процедурах ниже показано, как включить подтверждение подписи, используя элемент привязки <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="c1e50-106">The following procedures specify how to enable signature confirmation using an <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="c1e50-107">Аналогичным образом можно использовать элемент привязки <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="c1e50-107">You can use the same procedure with a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="c1e50-108">Процедура основана на основных шагах, описанных в разделе [инструкции. Создание пользовательской привязки с помощью SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="c1e50-108">The procedure builds upon the basic steps found in [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

### <a name="to-enable-signature-confirmation-in-code"></a><span data-ttu-id="c1e50-109">Включение подтверждения подписи в коде</span><span class="sxs-lookup"><span data-stu-id="c1e50-109">To enable signature confirmation in code</span></span>

1. <span data-ttu-id="c1e50-110">Создайте экземпляр класса <xref:System.ServiceModel.Channels.BindingElementCollection>.</span><span class="sxs-lookup"><span data-stu-id="c1e50-110">Create an instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class.</span></span>

2. <span data-ttu-id="c1e50-111">Создайте экземпляр <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> класса.</span><span class="sxs-lookup"><span data-stu-id="c1e50-111">Create an instance of the  <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> class.</span></span>

3. <span data-ttu-id="c1e50-112">Измените <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> на `true`.</span><span class="sxs-lookup"><span data-stu-id="c1e50-112">Set the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> to `true`.</span></span>

4. <span data-ttu-id="c1e50-113">Добавьте элемент безопасности в коллекцию элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="c1e50-113">Add the security element to the binding collection.</span></span>

5. <span data-ttu-id="c1e50-114">Создайте пользовательскую привязку, как указано в [инструкции. Создание пользовательской привязки с помощью SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="c1e50-114">Create a custom binding, as specified in [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

### <a name="to-enable-signature-confirmation-in-configuration"></a><span data-ttu-id="c1e50-115">Включение подтверждения подписи в конфигурации</span><span class="sxs-lookup"><span data-stu-id="c1e50-115">To enable signature confirmation in configuration</span></span>

1. <span data-ttu-id="c1e50-116">Добавьте элемент `<customBinding>` в раздел `<bindings>` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c1e50-116">Add a `<customBinding>` element to the `<bindings>` section of the configuration file.</span></span>

2. <span data-ttu-id="c1e50-117">Добавьте элемент `<binding>` и присвойте атрибуту имени соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="c1e50-117">Add a `<binding>` element and set the name attribute to an appropriate value.</span></span>

3. <span data-ttu-id="c1e50-118">Добавьте соответствующий элемент кодирования.</span><span class="sxs-lookup"><span data-stu-id="c1e50-118">Add an appropriate encoding element.</span></span> <span data-ttu-id="c1e50-119">В следующем примере добавляется элемент `<TextMessageEncoding>`.</span><span class="sxs-lookup"><span data-stu-id="c1e50-119">The following example adds a `<TextMessageEncoding>` element.</span></span>

4. <span data-ttu-id="c1e50-120">Добавьте дочерний элемент `<security>` и присвойте атрибуту `requireSignatureConfirmation` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="c1e50-120">Add a `<security>` child element and set the `requireSignatureConfirmation` attribute to `true`.</span></span>

5. <span data-ttu-id="c1e50-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="c1e50-121">Optional.</span></span> <span data-ttu-id="c1e50-122">Чтобы включить подтверждение подписи во время начальной загрузки, добавьте [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) дочерний элемент и присвойте `requireSignatureConfirmation` атрибуту значение `true` .</span><span class="sxs-lookup"><span data-stu-id="c1e50-122">To enable signature confirmation during the bootstrap, add a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element and set the `requireSignatureConfirmation` attribute to `true`.</span></span>

6. <span data-ttu-id="c1e50-123">Добавьте соответствующий элемент транспорта.</span><span class="sxs-lookup"><span data-stu-id="c1e50-123">Add an appropriate transport element.</span></span> <span data-ttu-id="c1e50-124">В следующем примере добавляется [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) :</span><span class="sxs-lookup"><span data-stu-id="c1e50-124">The following example adds an [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md):</span></span>

    ```xml
    <bindings>
      <customBinding>
        <binding name="SignatureConfirmationBinding">
          <security requireSignatureConfirmation="true">
            <secureConversationBootstrap requireSignatureConfirmation="true" />
              </security>
           <textMessageEncoding />
             <httpTransport />
        </binding>
      </customBinding>
    </bindings>
    ```

## <a name="example"></a><span data-ttu-id="c1e50-125">Пример</span><span class="sxs-lookup"><span data-stu-id="c1e50-125">Example</span></span>

<span data-ttu-id="c1e50-126">В приведенном ниже коде создается экземпляр класса <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> и свойству <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> присваивается значение `true`.</span><span class="sxs-lookup"><span data-stu-id="c1e50-126">The following code creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and sets the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> property to `true`.</span></span> <span data-ttu-id="c1e50-127">Обратите внимание, что в этом примере не используется элемент `<secureConversationBootstrap>`, показанный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="c1e50-127">Note that this example does not use the `<secureConversationBootstrap>` element shown in the preceding example.</span></span> <span data-ttu-id="c1e50-128">В этом примере демонстрируется подтверждение подписи при использовании маркера Windows (по протоколу Kerberos).</span><span class="sxs-lookup"><span data-stu-id="c1e50-128">This example demonstrates signature confirmation when using a Windows (Kerberos protocol) token.</span></span> <span data-ttu-id="c1e50-129">В данном случае подпись клиента возвращается во всех ответах службы и подтверждается клиентом.</span><span class="sxs-lookup"><span data-stu-id="c1e50-129">In this case, the signature of the client is returned in all responses from the service and is confirmed by the client.</span></span>

[!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
[!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]

## <a name="see-also"></a><span data-ttu-id="c1e50-130">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="c1e50-130">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>
- [<span data-ttu-id="c1e50-131">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="c1e50-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="c1e50-132">Практическое руководство. Создание SecurityBindingElement для заданного режима проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="c1e50-132">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
