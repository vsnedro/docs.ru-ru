---
title: Расширение системы метаданных
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: 7113120a3cde6b4e6a7eb1d329da625e25996952
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272987"
---
# <a name="extending-the-metadata-system"></a>Расширение системы метаданных

Система метаданных Windows Communication Foundation (WCF) — это группа классов и интерфейсов, представляющих метаданные, необходимые для реализации приложений на основе служб. Можно изменять или расширять классы, реализовывать и настраивать интерфейсы для экспорта и импорта пользовательских метаданных, например расширений языка WSDL или пользовательских утверждений WS-PolicyAttachments.  
  
## <a name="in-this-section"></a>в этом разделе  

 [Экспорт пользовательских метаданных для расширения WCF](exporting-custom-metadata-for-a-wcf-extension.md)  
 Содержит описание, как реализовать и использовать интерфейс <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> для внедрения в документы WSDL пользовательских утверждений политики.  
  
 [Импорт пользовательских метаданных для расширения WCF](importing-custom-metadata-for-a-wcf-extension.md)  
 Содержит описание, как реализовать и использовать интерфейс <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> для чтения пользовательских утверждений политики в документах WSDL и ответа на них.  
  
 [Публикация и получение метаданных через пользовательскую привязку](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 Содержит описание обмена данными для пользовательских привязок.
