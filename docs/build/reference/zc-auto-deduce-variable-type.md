---
title: "/Zc:auto (変数の型の推測) | Microsoft Docs"
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
  - "/Zc:auto"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc コンパイラ オプション (C++)"
  - "推測 (変数の型を) (C++)"
  - "Zc コンパイラ オプション (C++)"
  - "-Zc コンパイラ オプション (C++)"
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:auto (変数の型の推測)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Zc:auto\[\-\]** コンパイラ オプションは、変数を宣言するために [auto キーワード](../../cpp/auto-keyword.md)を使用する方法をコンパイラに伝えます。  既定のオプション **\/Zc:auto** を指定すると、コンパイラは宣言された変数の型を初期化式から推測します。   **\/Zc:auto\-** を指定すると、コンパイラは変数を自動ストレージ クラスに割り当てます。  
  
## 構文  
  
```  
/Zc:auto[-]  
```  
  
## 解説  
 C\+\+ 基準は、`auto` キーワードの元の意味と改定された意味を定義します。  [!INCLUDE[cpp_dev10_long](../Token/cpp_dev10_long_md.md)] より前までは、キーワードは自動ストレージ クラスで変数を宣言していました。つまりローカルの有効期間のある変数です。  [!INCLUDE[cpp_dev10_long](../Token/cpp_dev10_long_md.md)] からは、キーワードは宣言の初期化式から変数の種類を推測します。**\/Zc:auto\[\-\]** コンパイラ オプションを使って、`auto` キーワードの元の意味または改定された意味を使うようコンパイラに伝えます。  
  
 `auto` キーワードの使用が現在のコンパイラ オプションと矛盾している場合、コンパイラは適切な診断メッセージを発行します。  詳細については、「[auto キーワード](../../cpp/auto-keyword.md)」を参照してください。  Visual C\+\+ の準拠の問題の詳細については、「[非標準動作](../Topic/Nonstandard%20Behavior.md)」を参照してください。  
  
### このコンパイラ オプションを Visual Studio で使用するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードをクリックします。  
  
3.  **\[C\/C\+\+\]** ノードをクリックします。  
  
4.  **\[コマンド ライン\]** ノードをクリックします。  
  
5.  **\/Zc:auto** または **\/Zc:auto\-** を **\[追加オプション\]** ペインに追加します。  
  
## 参照  
 [\/Zc \(準拠\)](../../build/reference/zc-conformance.md)   
 [auto キーワード](../../cpp/auto-keyword.md)