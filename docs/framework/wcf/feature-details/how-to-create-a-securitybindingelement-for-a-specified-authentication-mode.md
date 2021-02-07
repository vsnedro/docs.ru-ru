---
description: Дополнительные сведения о том, как создать SecurityBindingElement для указанного режима проверки подлинности.
title: Практическое руководство. Создание SecurityBindingElement для заданного режима проверки подлинности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
ms.openlocfilehash: cb0831787b6d54daf561fc2750f1efe81bebfb0f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734481"
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a>Практическое руководство. Создание SecurityBindingElement для заданного режима проверки подлинности

Windows Communication Foundation (WCF) предоставляет несколько режимов, с помощью которых клиенты и службы проходят проверку подлинности друг за другом. Для этих режимов проверки подлинности можно создать привязки безопасности с помощью статических методов класса <xref:System.ServiceModel.Channels.SecurityBindingElement> или с помощью конфигурации, как показано в следующем примере кода.  
  
 Дополнительные сведения о 18 режимах проверки подлинности см. в статье [SecurityBindingElement Authentication modes](securitybindingelement-authentication-modes.md).  
  
## <a name="example"></a>Пример  

 В следующем примере кода показаны методы создания привязок для различных методов проверки подлинности.  
  
> [!NOTE]
> После создания объекта <xref:System.ServiceModel.Channels.SecurityBindingElement> некоторые свойства являются неизменяемыми, такие как <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> и <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>. Вызов `set` для этих свойств не изменяет их.  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a>См. также

- [Режимы проверки подлинности SecurityBindingElement](securitybindingelement-authentication-modes.md)
- [Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
