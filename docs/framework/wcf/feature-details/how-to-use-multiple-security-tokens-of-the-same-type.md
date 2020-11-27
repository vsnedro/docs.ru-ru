---
title: Практическое руководство. Использование нескольких маркеров безопасности одного типа
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
ms.openlocfilehash: 7374eebb9e42ef761b7ab8980b3eacf4d5671e6d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280706"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a>Практическое руководство. Использование нескольких маркеров безопасности одного типа

- В .NET Framework 3,0 клиентское сообщение содержит только один маркер любого заданного типа. Теперь клиентские сообщения могут содержать несколько маркеров одного типа. В этом разделе описывается, как включать в сообщение клиента несколько маркеров одного типа.  
  
- Обратите внимание, что настроить таким образом службу невозможно: служба может содержать только один вспомогательный маркер.  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a>Использование нескольких маркеров безопасности одного типа  
  
1. Создайте пустую коллекцию элементов привязки для заполнения.  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2. Создайте элемент привязки <xref:System.ServiceModel.Channels.SecurityBindingElement>, вызвав метод <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3. Создайте коллекцию <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters>.  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4. Добавьте в коллекцию маркеры SAML.  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5. Добавьте коллекцию к элементу привязки <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6. Добавьте элементы привязки в коллекцию элементов привязки.  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7. Верните новую пользовательскую привязку, созданную из коллекции элементов привязки.  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a>Пример  

 Ниже приводится весь метод, описанный в предыдущей процедуре.  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
