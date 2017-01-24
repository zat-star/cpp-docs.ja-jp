---
title: "CCommand クラス | Microsoft Docs"
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
  - "ATL::CCommand"
  - "CCommand"
  - "ATL.CCommand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCommand クラス"
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メソッドをコマンドを設定し、実行できるようになります。  
  
## 構文  
  
```  
template <  
   class TAccessor = CNoAccessor,  
   template < typename T > class TRowset = CRowset,  
   class TMultiple = CNoMultipleResults   
>  
class CCommand :   
   public CAccessorRowset <  
      TAccessor,   
      TRowset   
   >,  
   public CCommandBase,  
   public TMultiple  
```  
  
#### パラメーター  
 `TAccessor`  
 そのアクセサー クラスの型 \(`CDynamicParameterAccessor`、`CDynamicStringAccessor`、または `CEnumeratorAccessor`など\) を使用するコマンドがあります。  、クラスはサポート パラメーターまたは出力列に指定する既定 `CNoAccessor`です。  
  
 `TRowset`  
 その行セット クラスの種類 \(`CArrayRowset` または `CNoRowset`など\) を使用するコマンドがあります。  既定値は、`CRowset` です。  
  
 `TMultiple`  
 複数の結果を返すことができる OLE DB を指定します。[CMultipleResults](../../data/oledb/cmultipleresults-class.md)コマンドを使用するには、  それ以外の場合は [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)を使用します。  詳細については、「[IMultipleResults](https://msdn.microsoft.com/en-us/library/ms721289.aspx)」を参照してください。  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[&#91;閉じる&#93;](../Topic/CCommand::Close.md)|現在のコマンドを閉じます。|  
|[GetNextResult](../Topic/CCommand::GetNextResult.md)|複数の結果セットを使用すると、次の結果をフェッチします。|  
|[&#91;Open&#93;](../../data/oledb/ccommand-open.md)|コマンドを実行し、必要に応じてバインドします。|  
  
### 継承されたメソッド  
  
|||  
|-|-|  
|[Create](../../data/oledb/ccommand-create.md)|指定したセッションの新しいコマンドを作成し、コマンド テキストを設定します。|  
|[CreateCommand](../Topic/CCommand::CreateCommand.md)|新しいコマンドを作成します。|  
|[GetParameterInfo](../Topic/CCommand::GetParameterInfo.md)|コマンド パラメーター、名前、およびデータ型のリストを取得します。|  
|[準備します。](../../data/oledb/ccommand-prepare.md)|現在のコマンドを検証し、最適化します。|  
|[ReleaseCommand](../Topic/CCommand::ReleaseCommand.md)|パラメーター アクセサーを必要に応じて解放し、コマンドを解放します。|  
|[SetParameterInfo](../../data/oledb/ccommand-setparameterinfo.md)|各コマンド パラメーターのネイティブ型を指定します。|  
|[Unprepare](../../data/oledb/ccommand-unprepare.md)|現在のコマンド実行の計画を破棄します。|  
  
## 解説  
 パラメーター ベースの操作、またはコマンドを実行するときに、このクラスを使用してください。  だけ単純な行セットを開く必要がある場合 [CTable](../../data/oledb/ctable-class.md) を代わりに使用します。  
  
 使用するアクセサー クラスはバインディング パラメーターとデータのメソッドを決定します。  
  
 そのプロバイダーがストアド プロシージャをサポートしていないため、Jet で OLE DB のプロバイダーでストアド プロシージャを使用できないことに注意してください。定数だけがクエリ文字列で使用されます。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)