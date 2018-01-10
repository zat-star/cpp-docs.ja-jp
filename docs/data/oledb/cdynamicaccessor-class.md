---
title: "CDynamicAccessor クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicAccessor
- ATL::CDynamicAccessor
- CDynamicAccessor
dev_langs: C++
helpviewer_keywords: CDynamicAccessor class
ms.assetid: 374b13b7-1f09-457d-9e6b-df260ff4d178
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f88c3eff9c8160a0e322c93dacf6985dc7b8a20b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicaccessor-class"></a>CDynamicAccessor クラス
データベース スキーマ (データベースの基になる構造) の知識があるない場合にデータ ソースにアクセスできます。  
  
## <a name="syntax"></a>構文  
  
```  
class CDynamicAccessor : public CAccessorBase  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cdynamicaccessor-addbindentry.md)|既定のアクセサーをオーバーライドする場合は、出力列にバインド エントリを追加します。|  
|[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)|インスタンスを作成し、初期化、`CDynamicAccessor`オブジェクト。|  
|[閉じる](../../data/oledb/cdynamicaccessor-close.md)|すべての列をバインド解除、割り当て済みのメモリを解放し、解放、 [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx)クラスのインターフェイス ポインター。|  
|[GetBookmark](../../data/oledb/cdynamicaccessor-getbookmark.md)|現在の行のブックマークを取得します。|  
|[GetBlobHandling](../../data/oledb/cdynamicaccessor-getblobhandling.md)|現在の行の値を処理する BLOB を取得します。|  
|[GetBlobSizeLimit](../../data/oledb/cdynamicaccessor-getblobsizelimit.md)|BLOB の最大サイズ (バイト単位) を取得します。|  
|[GetColumnCount](../../data/oledb/cdynamicaccessor-getcolumncount.md)|行セットの列の数を取得します。|  
|[GetColumnFlags](../../data/oledb/cdynamicaccessor-getcolumnflags.md)|列の特性を取得します。|  
|[GetColumnInfo](../../data/oledb/cdynamicaccessor-getcolumninfo.md)|列のメタデータを取得します。|  
|[GetColumnName](../../data/oledb/cdynamicaccessor-getcolumnname.md)|指定された列の名前を取得します。|  
|[GetColumnType](../../data/oledb/cdynamicaccessor-getcolumntype.md)|指定された列のデータ型を取得します。|  
|[GetLength](../../data/oledb/cdynamicaccessor-getlength.md)|できる最大バイト数の列の長さを取得します。|  
|[GetOrdinal](../../data/oledb/cdynamicaccessor-getordinal.md)|列名を指定された列インデックスを取得します。|  
|[GetStatus](../../data/oledb/cdynamicaccessor-getstatus.md)|指定された列の状態を取得します。|  
|[GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)|バッファーからデータを取得します。|  
|[SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)|BLOB の現在の行の値の処理を設定します。|  
|[SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)|BLOB の最大サイズをバイト単位で設定します。|  
|[SetLength](../../data/oledb/cdynamicaccessor-setlength.md)|列の長さをバイト単位で設定します。|  
|[SetStatus](../../data/oledb/cdynamicaccessor-setstatus.md)|指定された列の状態を設定します。|  
|[SetValue](../../data/oledb/cdynamicaccessor-setvalue.md)|バッファーにデータを格納します。|  
  
## <a name="remarks"></a>コメント  
 使用して`CDynamicAccessor`列名、列数、データ型などの列情報を取得するメソッド。 この列の情報を使用するには、実行時に動的にアクセサーを作成します。  
  
 列情報が作成され、このクラスで管理されるバッファーに格納されます。 使用して、バッファーからデータを取得[GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)です。  
  
 ディスカッションと動的なアクセサー クラスを使用しての例では、次を参照してください。[動的アクセサーの使用](../../data/oledb/using-dynamic-accessors.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー**: atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor クラス](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)