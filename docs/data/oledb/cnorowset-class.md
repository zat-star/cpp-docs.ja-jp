---
title: "CNoRowset クラス | Microsoft Docs"
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
  - "ATL.CNoRowset"
  - "ATL::CNoRowset<TAccessor>"
  - "CNoRowset"
  - "ATL.CNoRowset<TAccessor>"
  - "ATL::CNoRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoRowset クラス"
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CNoRowset クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CCommand](../../data/oledb/ccommand-class.md) または [CTable](../../data/oledb/ctable-class.md)のテンプレート引数 \(`TRowset`\) として使用できます。  
  
## 構文  
  
```  
template <class TAccessor = CAccessorBase>  
class CNoRowset  
```  
  
#### パラメーター  
 `TAccessor`  
 アクセサー クラス。  既定値は、`CAccessorBase` です。  
  
## 解説  
 コマンドと行セットを返さなかった場合はテンプレート引数として `CNoRowset` を使用します。  
  
 `CNoRowset` は、それぞれが他のアクセサー クラスのメソッドに対応する次のメソッド スタブを実装します \(M:  
  
-   **BindFinished** \-バインドが完了するか \(戻り `S_OK`\)。  
  
-   **閉じる** \-リリース行と現在の IRowset インターフェイス。  
  
-   `GetIID` \-コネクション ポイント インターフェイスの ID を取得します。  
  
-   **GetInterface** \-インターフェイスを取得します。  
  
-   `GetInterfacePtr` \-カプセル化されたインターフェイス ポインターを取得します。  
  
-   **SetAccessor** \-設定アクセサーへのポインター。  
  
-   **SetupOptionalRowsetInterfaces** \-行セットの省略可能なインターフェイスを設定します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)