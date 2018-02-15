---
title: "CXMLAccessor クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CXMLAccessor
- CXMLAccessor
- ATL.CXMLAccessor
dev_langs:
- C++
helpviewer_keywords:
- CXMLAccessor class
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 00d9caa5c49d47eb005e85bdd715864651634a5a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="cxmlaccessor-class"></a>CXMLAccessor クラス
データ ストアのスキーマ (構造体の基になる) の知識があるない場合に文字列データとしてデータ ソースにアクセスできます。  
  
## <a name="syntax"></a>構文

```cpp
class CXMLAccessor : public CDynamicStringAccessorW  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md)|列情報を取得します。|  
|[GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md)|行で、テーブルの内容全体を取得します。|  
  
## <a name="remarks"></a>コメント  
 ただし、`CXMLAccessor`とは異なります`CDynamicStringAccessorW`を XML 形式のタグ付きデータとしてデータ ストアからすべてのデータに変換します。 これは、XML 対応の Web ページへの出力に特に便利です。 XML タグ名は、データ ストアの列名をできるだけ一致されます。  
  
 使用して`CDynamicAccessor`列情報を取得するメソッド。 実行時に動的にアクセサーを作成するのにには、この列の情報を使用します。  
  
 列の情報は、このクラスによって作成および管理のバッファーに格納されます。 列情報を使用して取得[GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md)を使用して行で列のデータを取得または[GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md)です。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/cpp/cxmlaccessor-class_1.cpp)]  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー**: atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor クラス](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CDynamicStringAccessor クラス](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicStringAccessorA クラス](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW クラス](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)