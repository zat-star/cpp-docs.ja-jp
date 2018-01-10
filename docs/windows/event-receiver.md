---
title: "event_receiver |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.event_receiver
dev_langs: C++
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 50ea26172e2f5112e760aa02d9247d07afbead2b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="eventreceiver"></a>event_receiver
イベント レシーバー (シンク) を作成します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ event_receiver(  
   type   
   [, layout_dependent=false]   
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `type`  
 次の値のいずれかの列挙です。  
  
-   `native`アンマネージ コードと C/C++ コード (ネイティブ クラスの既定値)。  
  
-   COM コード用の`com` 。 この値の場合、ユーザーが次のヘッダー ファイルを含める必要があります。  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **layout_dependent**  
 指定*layout_dependent*場合にのみ、 `type` = **com**です。*layout_dependent*はブール値。  
  
-   **true**ことに、イベント レシーバー必要がありますと正確に一致するが、フックのイベント ソースで、デリゲートのシグネチャを意味します。 イベント レシーバーのハンドラー名は、関連するイベント ソース インターフェイスで指定された名前に一致する必要があります。 使用する必要があります**コクラス**とき*layout_dependent*は**true**です。 指定するやや効率的である**true**です。  
  
-   **false** (既定値) ことを意味する呼び出し規約とストレージ クラス (virtual、static、およびその他の) イベント メソッドとハンドラー; に一致する必要はありませんやハンドラー名は、イベント ソース インターフェイス メソッドの名前と一致する必要があります。  
  
## <a name="remarks"></a>コメント  
 **Event_receiver** C++ 属性は、クラスまたは構造体を適用するによって、Visual C の統合イベント モデルを使用して、イベント レシーバーができることを指定します。  
  
 **event_receiver**と共に使用される、 [event_source](../windows/event-source.md)属性および[_ _hook](../cpp/hook.md)と[_ _unhook](../cpp/unhook.md)キーワード。 使用して**event_source**イベント ソースを作成します。 使用して`__hook`(「フック」) イベント レシーバー メソッドをイベント ソースのイベントを関連付けるには、イベント レシーバーのメソッド内にあります。 使用して`__unhook`の関連付けを解除しています。  
  
 *layout_dependent*は COM イベント レシーバーにのみ指定 (`type`=**com**)。 既定の*layout_dependent*は**false**です。  
  
> [!NOTE]
>  テンプレート クラスまたは構造体にイベントを含めることはできません。  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、 `struct`|  
|**反復可能**|×|  
|**必要な属性**|**コクラス**とき*layout_dependent*=**は true。**|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [コンパイラ属性](../windows/compiler-attributes.md)   
 [event_source](../windows/event-source.md)   
 [_ _event](../cpp/event.md)   
 [_ _hook します。](../cpp/hook.md)   
 [_ _unhook](../cpp/unhook.md)   
 [クラス属性](../windows/class-attributes.md)   
