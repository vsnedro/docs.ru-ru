---
title: Практическое руководство. Порядок отключения безопасных сеансов в WSFederationHttpBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 675fa143-6a4e-4be3-8afc-673334ab55ec
ms.openlocfilehash: df057d64feb89d1e43b938b36cb48f2f103b17d0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595392"
---
# <a name="how-to-disable-secure-sessions-on-a-wsfederationhttpbinding"></a>Практическое руководство. Порядок отключения безопасных сеансов в WSFederationHttpBinding

Некоторые службы могут требовать федеративных учетных данных, но не поддерживать безопасные сеансы. В этом случае необходимо отключить возможность безопасных сеансов. В отличие от класса <xref:System.ServiceModel.WSHttpBinding>, класс <xref:System.ServiceModel.WSFederationHttpBinding> не предоставляет способа отключения безопасных сеансов при взаимодействии со службой. Вместо этого необходимо создать пользовательскую привязку, которая заменяет параметры безопасного сеанса начальной загрузкой.

В этом разделе показано, как изменить элементы привязки, содержащиеся в привязке <xref:System.ServiceModel.WSFederationHttpBinding>, чтобы создать пользовательскую привязку. Результат совпадает с <xref:System.ServiceModel.WSFederationHttpBinding>, за исключением того, что не используются безопасные сеансы.

## <a name="to-create-a-custom-federated-binding-without-secure-session"></a>Создание пользовательской федеративной привязки без безопасных сеансов

1. Создайте экземпляр класса <xref:System.ServiceModel.WSFederationHttpBinding> либо принудительно в коде, либо загрузив один из файлов конфигурации.

2. Клонируйте <xref:System.ServiceModel.WSFederationHttpBinding> в <xref:System.ServiceModel.Channels.CustomBinding>.

3. Найдите <xref:System.ServiceModel.Channels.SecurityBindingElement> в <xref:System.ServiceModel.Channels.CustomBinding>.

4. Найдите <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> в <xref:System.ServiceModel.Channels.SecurityBindingElement>.

5. Замените исходный элемент <xref:System.ServiceModel.Channels.SecurityBindingElement> элементом привязки безопасности начальной загрузки из <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>.

## <a name="example"></a>Пример

В следующем примере создается пользовательская федеративная привязка без безопасных сеансов.

[!code-csharp[c_CustomFederationBinding#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customfederationbinding/cs/c_customfederationbinding.cs#0)]
[!code-vb[c_CustomFederationBinding#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customfederationbinding/vb/c_customfederationbinding.vb#0)]

## <a name="compiling-the-code"></a>Компиляция кода

- Чтобы скомпилировать этот пример кода, создайте проект, ссылающийся на сборку System.ServiceModel.dll.

## <a name="see-also"></a>Дополнительно

- [Привязки и безопасность](bindings-and-security.md)
