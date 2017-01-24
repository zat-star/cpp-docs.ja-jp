---
title: "pgomgr | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "pgomgr プログラム"
  - "ガイド付き最適化のプロファイル, pgomgr"
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pgomgr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

1 つ以上の .pgc ファイルから .pgd ファイルにプロファイル データを追加します。  
  
## 構文  
  
```  
pgomgr [options] pgcfiles pgdfile  
```  
  
#### パラメーター  
 `options`  
 pgomgr には、次のオプションを指定できます。  
  
 **\/help —** 使用できる pgomgr オプションを表示します \(省略形は \/?\)。  
  
 **\/clear —** .pgd ファイルからすべてのプロファイル情報を消去します。  **\/clear** が指定されているときは、.pgc ファイルを指定できません。  
  
 **\/detail** — フロー グラフのカバレージ情報を含む詳細な統計情報を表示します。  
  
 **\/summary** — 関数ごとの統計情報を表示します。  
  
 **\/unique** — **\/summary** と共に使用されている場合は、装飾された関数名が表示されます。既定では \/unique は指定されず、装飾されていない関数名が表示されます。  
  
 **\/merge**\[**:***n*\] **—** 1 つ以上の .pgc ファイルのデータを .pgd ファイルに追加します。省略可能なパラメーター *n* を使用すると、データを *n* 回追加することを指定できます。たとえば、通常 6 回実行するシナリオであれば、テスト実行で一度実行した後で **pgomgr \/merge:6** を指定して、そのデータを .pgd ファイルに 6 回追加できます。  
  
 `pgcfiles`  
 .pgd ファイルにマージするプロファイル データが含まれている、1 つ以上の .pgc ファイル。  .pgc ファイルは、1 つだけ指定することも複数指定することもできます。  .pgc ファイルを指定しないと、pgomgr は .pgd ファイルと同じファイル名の .pgc ファイルをすべてマージします。  
  
 `pgdfile`  
 1 つ以上の .pgc ファイルからデータをマージする .pgd ファイル。  
  
## 解説  
  
> [!NOTE]
>  このツールは、[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] コマンド プロンプトからのみ開始できます。  システム コマンド プロンプトやエクスプローラーからは開始できません。  
  
## 使用例  
 次の例では、.pgd ファイルからプロファイル データが消去されます。  
  
```  
pgomgr /clear myapp.pgd  
```  
  
 次の例では、myapp1.pgc のプロファイル データが .pgd ファイルに 3 回追加されます。  
  
```  
pgomgr /merge:3 myapp1.pgc myapp.pgd  
```  
  
 次の例では、すべての myapp\#.pgc ファイルのプロファイル データが myapp.pgd ファイルに追加されます。  
  
```  
pgomgr -merge myapp1.pgd  
```  
  
## 参照  
 [ガイド付き最適化のプロファイル用ツール](../../build/reference/tools-for-manual-profile-guided-optimization.md)