---
description: Дополнительные сведения см. в статье как настроить подтверждение подписи.
title: Практическое руководство. Настройка подтверждения сигнатуры
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signature confirmation
- WCF, security
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
ms.openlocfilehash: 158ec2a5f74038f5c1ca1af847f57457a8881974
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643193"
---
# <a name="how-to-set-up-a-signature-confirmation"></a>Практическое руководство. Настройка подтверждения сигнатуры

*Подтверждение сигнатуры* — это механизм для инициатора сообщений, гарантирующий, что полученный ответ был создан в ответ на исходное сообщение отправителя. Подтверждение подписи определено в спецификации WS-Security 1.1. Если конечная точка поддерживает WS-Security 1.0, использовать подтверждение подписи нельзя.

В процедурах ниже показано, как включить подтверждение подписи, используя элемент привязки <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. Аналогичным образом можно использовать элемент привязки <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>. Процедура основана на основных шагах, описанных в разделе [инструкции. Создание пользовательской привязки с помощью SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).

### <a name="to-enable-signature-confirmation-in-code"></a>Включение подтверждения подписи в коде

1. Создайте экземпляр класса <xref:System.ServiceModel.Channels.BindingElementCollection>.

2. Создайте экземпляр  <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> класса.

3. Измените <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> на `true`.

4. Добавьте элемент безопасности в коллекцию элементов привязки.

5. Создайте пользовательскую привязку, как указано в [инструкции. Создание пользовательской привязки с помощью SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).

### <a name="to-enable-signature-confirmation-in-configuration"></a>Включение подтверждения подписи в конфигурации

1. Добавьте элемент `<customBinding>` в раздел `<bindings>` файла конфигурации.

2. Добавьте элемент `<binding>` и присвойте атрибуту имени соответствующее значение.

3. Добавьте соответствующий элемент кодирования. В следующем примере добавляется элемент `<TextMessageEncoding>`.

4. Добавьте дочерний элемент `<security>` и присвойте атрибуту `requireSignatureConfirmation` значение `true`.

5. Необязательный элемент. Чтобы включить подтверждение подписи во время начальной загрузки, добавьте [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) дочерний элемент и присвойте `requireSignatureConfirmation` атрибуту значение `true` .

6. Добавьте соответствующий элемент транспорта. В следующем примере добавляется [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) :

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

## <a name="example"></a>Пример

В приведенном ниже коде создается экземпляр класса <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> и свойству <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> присваивается значение `true`. Обратите внимание, что в этом примере не используется элемент `<secureConversationBootstrap>`, показанный в предыдущем примере. В этом примере демонстрируется подтверждение подписи при использовании маркера Windows (по протоколу Kerberos). В данном случае подпись клиента возвращается во всех ответах службы и подтверждается клиентом.

[!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
[!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>
- [Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Практическое руководство. Создание SecurityBindingElement для заданного режима проверки подлинности](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
