---
title: Привязки WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 94f0ba602cd1f58f5491a44a64e24be8ea52895b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293992"
---
# <a name="ws-metadataexchange-bindings"></a>Привязки WS-MetadataExchange

В этом разделе описано, как создавать привязки обмена метаданными по умолчанию для различных транспортов.  
  
## <a name="the-default-bindings"></a>Привязки по умолчанию  
  
|Имя привязки по умолчанию|Создание привязки|  
|--------------------------|------------------------------------|  
|mexHttpBinding|Привязка <xref:System.ServiceModel.WSHttpBinding> с отключенной безопасностью транспортного уровня.|  
|mexHttpsBinding|Привязка <xref:System.ServiceModel.WSHttpBinding> с поддержкой безопасности транспортного уровня.|  
|mexNamedPipeBinding|Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> и значениями по умолчанию.|  
|mexTcpBinding|Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.TcpTransportBindingElement> и значениями по умолчанию.|
