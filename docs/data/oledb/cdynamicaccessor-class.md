---
title: "CDynamicAccessor クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CDynamicAccessor"
  - "ATL::CDynamicAccessor"
  - "CDynamicAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicAccessor クラス"
ms.assetid: 374b13b7-1f09-457d-9e6b-df260ff4d178
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データベース スキーマ \(データベースの基になる構造\) が不明な場合にデータ ソースにアクセスできます。  
  
## 構文  
  
```  
class CDynamicAccessor : public CAccessorBase  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cdynamicaccessor-addbindentry.md)|既定のアクセサーをオーバーライドする場合は、出力列にバインド エントリを追加します。|  
|[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)|`CDynamicAccessor` オブジェクトをインスタンス化し、初期化します。|  
|[&#91;閉じる&#93;](../../data/oledb/cdynamicaccessor-close.md)|すべての列をバインドし、割り当てたメモリを解放し、そのクラスの [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) インターフェイス ポインターを解放します。|  
|[GetBookmark](../../data/oledb/cdynamicaccessor-getbookmark.md)|現在の行のブックマークを取得します。|  
|[GetBlobHandling](../../data/oledb/cdynamicaccessor-getblobhandling.md)|現在の行の BLOB の処理値を取得します。|  
|[GetBlobSizeLimit](../../data/oledb/cdynamicaccessor-getblobsizelimit.md)|最大バイト BLOB のサイズを取得します。|  
|[GetColumnCount](../../data/oledb/cdynamicaccessor-getcolumncount.md)|行セットの列の数を取得します。|  
|[GetColumnFlags](../../data/oledb/cdynamicaccessor-getcolumnflags.md)|列の特性を取得します。|  
|[GetColumnInfo](../../data/oledb/cdynamicaccessor-getcolumninfo.md)|列のメタデータを取得します。|  
|[GetColumnName](../Topic/CDynamicAccessor::GetColumnName.md)|指定された列の名前を取得します。|  
|[GetColumnType](../../data/oledb/cdynamicaccessor-getcolumntype.md)|指定した列のデータ型を取得します。|  
|[GetLength](../../data/oledb/cdynamicaccessor-getlength.md)|バイト列の最大の長さを取得します。|  
|[GetOrdinal](../../data/oledb/cdynamicaccessor-getordinal.md)|項目の名前を持つ列インデックスを取得します。|  
|[GetStatus](../../data/oledb/cdynamicaccessor-getstatus.md)|指定された列の状態を取得します。|  
|[GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)|バッファーからデータを取得します。|  
|[SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)|現在の行の BLOB の処理値を設定します。|  
|[SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)|最大バイト BLOB のサイズを設定します。|  
|[SetLength](../../data/oledb/cdynamicaccessor-setlength.md)|バイト列の長さを設定します。|  
|[SetStatus](../Topic/CDynamicAccessor::SetStatus.md)|指定された列の状態を設定します。|  
|[SetValue](../../data/oledb/cdynamicaccessor-setvalue.md)|バッファーにデータを保存します。|  
  
## 解説  
 項目の名前などの列情報、列数、データ型を取得するために `CDynamicAccessor` などのメソッドを使用します。  次実行時にアクセサーを動的に作成するときにもこの列情報を使用します。  
  
 列情報は、このクラスによって作成および管理されるバッファーに格納されます。  [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)を使用してバッファーからデータを取得します。  
  
 動的なアクセサー クラスを説明と使用例については、[動的なアクセサーを使用して](../../data/oledb/using-dynamic-accessors.md)を参照してください。  
  
## 必要条件  
 **ヘッダー**: atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor クラス](../Topic/CAccessor%20Class.md)   
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor クラス](../Topic/CManualAccessor%20Class.md)