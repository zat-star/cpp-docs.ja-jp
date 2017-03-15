---
title: "ストアド プロシージャの使用 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB プロバイダー テンプレート, ストアド プロシージャ"
  - "OLE DB, ストアド プロシージャ"
  - "ストアド プロシージャ, ストアド プロシージャの概要"
  - "ストアド プロシージャ, OLE DB"
  - "ストアド プロシージャ, Visual C++"
ms.assetid: 90507e4c-eca2-46c9-ad8c-07e10dc1d41b
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# ストアド プロシージャの使用
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストアド プロシージャは、データベースに格納されている実行可能なオブジェクトです。  ストアド プロシージャの呼び出しは、SQL コマンドの呼び出しと似ています。  クライアント アプリケーションでステートメントを実行または準備する代わりに、データ ソースに対してストアド プロシージャを使用すると、パフォーマンスの向上、ネットワーク オーバーヘッドの削減、一貫性と正確性の向上などのさまざまな利点が得られます。  
  
 ストアド プロシージャは、任意の数 \(ゼロを含む\) の入力または出力パラメーターを持つことができ、戻り値を返すことができます。  パラメーター値を特定のデータ値としてハードコーディングすることも、パラメーター マーカー \(疑問符 "?"\) を使用することもできます。  
  
> [!NOTE]
>  Visual C\+\+ を使って作成した CLR の SQL Server ストアド プロシージャは、**\/clr:safe** コンパイラ オプションでコンパイルする必要があります。  
  
 SQL Server 用の OLE DB プロバイダー \(SQLOLEDB\) は、ストアド プロシージャがデータを返すために使用する以下の機構をサポートします。  
  
-   プロシージャ内のすべての SELECT ステートメントは結果セットを生成します。  
  
-   プロシージャは、出力パラメーターを通じてデータを返すことができます。  
  
-   プロシージャは、整数のリターン コードを持つことができます。  
  
> [!NOTE]
>  OLE DB Provider for Jet はストアド プロシージャをサポートしていないため、このプロバイダーではストアド プロシージャを使用できません。クエリ文字列には定数だけを使用できます。  
  
## 参照  
 [OLE DB コンシューマー テンプレートの操作](../../data/oledb/working-with-ole-db-consumer-templates.md)