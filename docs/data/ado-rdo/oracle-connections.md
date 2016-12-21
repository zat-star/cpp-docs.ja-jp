---
title: "Oracle 接続 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "接続 [C++], データベース"
  - "データベース接続 [C++], Oracle"
  - "データベース [C++], 接続"
  - "Oracle [C++], 作成 (接続を)"
  - "Oracle データベース [C++]"
  - "Oracle データベース [C++], 接続"
ms.assetid: d317e763-44aa-47c9-abe8-261d513d894f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Oracle 接続
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Oracle ODBC DSN または OLE DB 接続を設定する場合は、あらかじめ Oracle の SQL\*Net クライアント側コンポーネントをインストールする必要があります。  SQL\*Net は、Oracle のネットワーク トランスポート層です。  ほとんどの Oracle ODBC ドライバーは、この SQL\*Net 層を直接呼び出します。これは、Microsoft 社製ドライバーと Microsoft OLE DB Oracle プロバイダー マップにも当てはまります。  
  
 SQL\*Net の構成が完了したら、SQL\*Net の接続文字列を確認します。  通常、この文字列は、Oracle データベース サーバー名とネットワーク プロトコルの種類 \(TCP\/IP や名前付きパイプなど\) の指定子で構成されます。  この SQL\*Net 接続文字列が別名に対応付けられていることもあります。  このような場合は、別名を書き留めるだけで十分です。  SQL\*Net を設定する方法については、Oracle DB の管理者にご相談ください。または、SQL\*Net のドキュメントを参照するか、Oracle ODBC ドライバーのヘルプ ファイルで接続文字列の例を参照してください。  
  
## 参照  
 [データベース接続を作成する](../Topic/Creating%20Database%20Connections.md)