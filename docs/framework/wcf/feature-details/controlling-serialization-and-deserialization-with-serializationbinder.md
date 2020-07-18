---
title: Управление сериализацией и десериализацией с помощью SerializationBinder
ms.date: 07/14/2020
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
ms.openlocfilehash: 5a7d0bf2aabfcdf789a77cf0fcfeb26357575806
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2020
ms.locfileid: "86444486"
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a>Управление сериализацией и десериализацией с помощью SerializationBinder

> [!WARNING]
> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>не является безопасным и ***не*** может быть обеспечена безопасным. Дополнительные сведения см. в разделе [BinaryFormatter Security Guide](../../../standard/serialization/binaryformatter-security-guide.md).

При сериализации модуль форматирования передает сведения, необходимые для создания экземпляра объекта правильных типа и версии. Эти сведения обычно содержат полное имя типа и имя сборки объекта. По умолчанию с помощью этих сведений операция десериализации создает экземпляр такого же объекта. Некоторым пользователям может понадобиться возможность выбирать классы для сериализации и десериализации, поскольку исходный класс может отсутствовать на компьютере, где выполняется десериализация, быть перемещенным в другую сборку либо на сервере и клиенте могут требоваться разные версии класса. Дополнительные сведения см. в разделе [Использование связывателя сериализации](../samples/usage-of-serialization-binder.md).  
  
> [!WARNING]
> Эта функция доступна только при использовании <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> или <xref:System.Runtime.Serialization.NetDataContractSerializer>.  
  
## <a name="using-serializationbinder"></a>Использование класса SerializationBinder  
 Класс <xref:System.Runtime.Serialization.SerializationBinder> является абстрактным классом, который используется для управления фактическими типами, применяемыми при сериализации и десериализации. Чтобы управлять типами, используемыми при сериализации и десериализации, нужно создать класс, производный от класса <xref:System.Runtime.Serialization.SerializationBinder>, и переопределить методы <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> и <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)>. Метод <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> принимает объект <xref:System.Type> и возвращает имя типа и сборки. Метод <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> принимает имя сборки и типа и возвращает объект <xref:System.Type>.  
  
## <a name="see-also"></a>Дополнительно

- [Сериализация и десериализация](serialization-and-deserialization.md)
- [Использование средства привязки сериализации](../samples/usage-of-serialization-binder.md)
