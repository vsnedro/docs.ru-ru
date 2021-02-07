---
description: 'Дополнительные сведения: как использовать несколько маркеров безопасности одного типа'
title: Практическое руководство. Использование нескольких маркеров безопасности одного типа
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
ms.openlocfilehash: 0cbf831c82fdc2aee5a09237c586286a5776d234
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734260"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a>Практическое руководство. Использование нескольких маркеров безопасности одного типа

- В платформа .NET Framework 3,0 клиентское сообщение содержит только один маркер любого заданного типа. Теперь клиентские сообщения могут содержать несколько маркеров одного типа. В этом разделе описывается, как включать в сообщение клиента несколько маркеров одного типа.  
  
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
