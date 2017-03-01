---
title: "Concurrency 名前空間を持つ列挙型 (AMP) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: b9555023e01cb765ca943fcaaf785cdc2b4e2d0d
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-enums-amp"></a>Concurrency 名前空間を持つ列挙型 (AMP)
|||  
|-|-|  
|[access_type 列挙型](#access_type)|[queuing_mode 列挙型](#queuing_mode)|  
  
##  <a name="a-nameaccesstypea--accesstype-enumeration"></a><a name="access_type"></a>access_type 列挙型  
 データへのさまざまな種類のアクセスを示すために使用される列挙型。  
  
```  
enum access_type;  
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`access_type_auto`|アクセラレータに最も適した `access_type` を自動的に選択します。|  
|`access_type_none`|専用。 割り当ては、アクセラレータ上でのみアクセスでき、CPU 上ではアクセスできません。|  
|`access_type_read`|共有。 割り当ては、アクセラレータ上でアクセスでき、CPU 上では読み取り可能です。|  
|`access_type_read_write`|共有。 割り当ては、アクセラレータ上でアクセスでき、CPU 上では書き込み可能です。|  
|`access_type_write`|共有。 割り当ては、アクセラレータ上でアクセスでき、CPU 上では読み取りおよび書き込みの両方ができます。|  

  
##  <a name="a-namequeuingmodea--queuingmode-enumeration"></a><a name="queuing_mode"></a>queuing_mode 列挙型  
 アクセラレータでサポートされているキュー モードを指定します。  
  
```  
enum queuing_mode;  
``` 
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`queuing_mode_immediate`|などのことを指定するキュー モード コマンド[parallel_for_each 関数 (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)、呼び出し元に戻るとすぐに対応するアクセラレータ デバイスに送信されます。|  
|`queuing_mode_automatic`|対応するコマンド キューに入れられるコマンドを指定するキュー モード、 [accelerator_view](accelerator-view-class.md)オブジェクトです。 コマンドは、デバイスに送信されるときに[accelerator_view::flush](accelerator-view-class.md#flush)が呼び出されます。|   
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

