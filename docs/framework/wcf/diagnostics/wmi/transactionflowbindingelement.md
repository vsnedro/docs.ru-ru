---
description: 'Дополнительные сведения о: Трансактионфловбиндинжелемент'
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: 6a96a83c563affdaef01a12d64bc1c13ab2f719e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757141"
---
# <a name="transactionflowbindingelement"></a>TransactionFlowBindingElement

TransactionFlowBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a>Методы  

 Класс TransactionFlowBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  

 Класс TransactionFlowBindingElement имеет следующие свойства.  
  
### <a name="issuedtokens"></a>IssuedTokens  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Задает требование для заголовка выданных маркеров безопасности (IssuedTokens из WS-Trust).  
  
### <a name="transactionprotocol"></a>TransactionProtocol  

 Тип данных: строка  
  
 Тип доступа: только для чтения  
  
 Протокол транзакций, используемый службой для передачи транзакций.  
  
### <a name="transactions"></a>Transactions  

 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, поддерживается ли входящая транзакция.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
