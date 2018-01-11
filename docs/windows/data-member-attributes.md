---
title: "データ メンバー属性 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- attributes [C++], reference topics
- data members [C++], attributes
- data members [C++]
ms.assetid: 95b2397d-1daf-4ae4-8cd0-06956d005b13
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 954a0448f160ba6d19eb4f48d44b0b7e0a718f17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="data-member-attributes"></a>データ メンバー属性
次の属性は、クラス、コクラス、またはインターフェイス内のデータ メンバーに適用されます。  
  
|属性|説明|  
|---------------|-----------------|  
|[db_accessor](../windows/db-accessor.md)|グループ**db_column**に参加している属性`IAccessor`-ベースのバインディングです。|  
|[db_column](../windows/db-column.md)|行セットに指定された列をバインドします。|  
|[db_command](../windows/db-command.md)|OLE DB コマンドを作成します。|  
|[db_param](../windows/db-param.md)|入力または出力パラメーターを持つ指定したメンバー変数を関連付けるし、変数を区切ります。|  
|[db_source](../windows/db-source.md)|データ ソースへの接続を作成します。|  
|[db_table](../windows/db-table.md)|OLE DB テーブルを開きます。|  
|[defaultbind](../windows/defaultbind.md)|1 つのバインド可能なプロパティ オブジェクトを最も良く表すものを示します。|  
|[displaybind](../windows/displaybind.md)|バインド可能なとしてユーザーに表示されるプロパティを示します。|  
|[ID](../windows/id.md)|メンバー関数 (プロパティまたはメソッド、インターフェイスまたはディスパッチ インターフェイス) の DISPID を指定します。|  
|[範囲](../windows/range-cpp.md)|引数または値が設定される実行時にフィールドに使用できる値の範囲を指定します。|  
|[rdx](../windows/rdx.md)|レジストリ キーを作成するか、既存のレジストリ キーを変更します。|  
|[readonly](../windows/readonly-cpp.md)|データ メンバーへの割り当てを禁止します。|  
|[requestedit](../windows/requestedit.md)|プロパティをサポートしていることを示します、 **OnRequestEdit**通知します。|  
  
## <a name="see-also"></a>参照  
 [使用法別の属性](../windows/attributes-by-usage.md)