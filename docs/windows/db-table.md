---
title: "db_table |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.db_table
dev_langs:
- C++
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 37dd6fd80a0d18f1b9d93f5299fca797238a509f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="dbtable"></a>db_table
OLE DB テーブルを開きます。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ db_table(   
   db_table,   
   name,   
   source_name,   
   hresult   
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *db_table*  
 ("Products"など) などのデータベース テーブルの名前を指定する文字列。  
  
 *name* (省略可能)  
 テーブルを操作に使用するためのハンドルの名前。 結果の 2 つ以上の行を取得する場合は、このパラメーターを指定する必要があります。 **db_table** 、指定された変数が生成されます*名前*行セットをスキャンまたは複数のアクションのクエリの実行に使用できます。  
  
 *source_name* (省略可能)  
 `CSession` 変数、または `db_source` 属性が適用された、コマンドが実行されるクラスのインスタンス。 「 [db_source](../windows/db-source.md)」をご覧ください。  
  
 `hresult` (省略可能)  
 このデータベース コマンドの `HRESULT` を受け取る変数を示します。 変数が存在しない場合は、属性によって自動的に挿入されます。  
  
## <a name="remarks"></a>コメント  
 **db_table**を作成、 [CTable](../data/oledb/ctable-class.md)を開くには、テーブル、OLE DB コンシューマーによって使用されるオブジェクト。 この属性をクラス レベルでのみ使用できます。インラインを使用することはできません。 使用して**db_column**テーブルの列を変数にバインドする使用**db_param**を区切るために (パラメーターの型などで設定) のパラメーターです。  
  
 コンシューマー属性プロバイダーは、クラスにこの属性を適用する場合、コンパイラの名前は変更するクラス\_*すると*アクセサー、場所*すると*指定した名前は、クラス、および、コンパイラと呼ばれるクラスを作成また*すると*から派生した\_*すると*アクセサー。  クラス ビューでは、両方のクラスが表示されます。  
  
## <a name="example"></a>例  
 次の例で使用するため、Products テーブルを開きます`CProducts`です。  
  
```  
// db_table.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_table(L"dbo.Products") ]  
class CProducts {  
   [ db_column("1") ] LONG m_ProductID;  
};  
```  
  
 アプリケーションで使用されるこの属性の例は、サンプルを参照してください。 [AtlAgent](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409)と[MultiRead](http://msdn.microsoft.com/en-us/5a2a915a-77dc-492f-94b2-1b809995dd5e)です。  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、 `struct`|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー属性](../windows/ole-db-consumer-attributes.md)   
