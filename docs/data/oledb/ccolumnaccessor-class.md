---
title: "CColumnAccessor クラス | Microsoft Docs"
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
  - "CColumnAccessor"
  - "ATL::CColumnAccessor"
  - "ATL.CColumnAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CColumnAccessor クラス"
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CColumnAccessor クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

generates コンシューマー コードを挿入します。  
  
## 構文  
  
```  
class CColumnAccessor : public CAccessorBase  
```  
  
## 解説  
 挿入されたコードの各列が別のアクセサーとしてバインドされます。  デバッグ時にこのクラスが挿入されたコード \(たとえば、もあります\) を使用した、通常、プロパティ、またはメソッドを直接使用する必要がないことに注意してください。  
  
 `CColumnAccessor` は、それぞれが他のアクセサー クラスのメソッドに対応する次のメソッド スタブを実装します \(M:  
  
-   `CColumnAccessor`;コンストラクター `CColumnAccessor` オブジェクトをインスタンス化し、初期化します。  
  
-   `CreateAccessor`には、列バインディング構造体のメモリを割り当て、列データ メンバーを初期化します。  
  
-   アクセサーの**BindColumns**の列をバインドできます。  
  
-   **SetParameterBuffer**はパラメーターのバッファーを割り当てます。  
  
-   `AddParameter`はパラメーター エントリ パラメーターにエントリを追加します。  
  
-   **HasOutputColumns**はアクセサーが出力列が含まれるかどうかを判定します。  
  
-   **HasParameters**はアクセサーはパラメーターが存在するかどうかを判定します。  
  
-   `BindParameters`が列に作成されたパラメーターをバインドします。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)