---
title: "致命的なエラー C1004 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1004"
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 致命的なエラー C1004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

予期しない EOF が見つかりました。  
  
 構成体の展開処理を終了する前にソース ファイルの末尾に到達しました。  以下のいずれかの要素がコードで指定されていない可能性があります。  
  
-   右中かっこ \(}\)  
  
-   右かっこ \( \) \)  
  
-   コメント終端記号 \(\*\/\)  
  
-   セミコロン \(;\)  
  
 このエラーを解決するには、以下を確認します。  
  
-   既定のディスク ドライブに一時ファイル作成ための十分な領域がありません。ソース ファイルの約 2 倍の領域が必要になります。  
  
-   false と評価された `#if` ディレクティブに対応する `#endif` ディレクティブがありません。  
  
-   ソース ファイルの末尾にキャリッジ リターンとライン フィードがありません。  
  
 次の例では警告 C1004 が生成されます。  
  
```  
// C1004.cpp  
#if TEST  
int main() {}  
// C1004  
```  
  
 解決方法 :  
  
```  
// C1004b.cpp  
#if TEST  
#endif  
  
int main() {}  
```