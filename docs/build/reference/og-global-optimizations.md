---
title: "/Og (グローバルの最適化) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.GlobalOptimizations"
  - "/og"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Og コンパイラ オプション [C++]"
  - "自動レジスタ割り当て"
  - "共通部分式の削除"
  - "グローバルな最適化のコンパイラ オプション [C++]"
  - "ループ構造, 最適化"
  - "Og コンパイラ オプション [C++]"
  - "-Og コンパイラ オプション [C++]"
ms.assetid: d10630cc-b9cf-4e97-bde3-8d7ee79e9435
caps.latest.revision: 17
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Og (グローバルの最適化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ローカルおよびグローバルな最適化、自動レジスタ割り当て、およびループ最適化を行います。  使用は推奨されていません。  
  
## 構文  
  
```  
/Og  
```  
  
## 解説  
 使用できる最適化は次のとおりです。  
  
-   ローカルおよびグローバルの共通部分式の削除  
  
     この最適化を行うと、共通部分式の値が 1 回だけ計算されます。  次の例では、3 つの式の間で `b` と `c` の値が変更されない場合、 `b + c` の計算結果がテンポラリ変数に代入され、`b + c` の代わりにこのテンポラリ変数が使用されます。  
  
    ```  
    a = b + c;  
    d = b + c;  
    e = b + c;  
    ```  
  
     共通部分式をローカルに最適化すると、コンパイラは短いコード セクション内で共通の部分式を探します。  グローバルに最適化すると、すべての関数に共通の部分式を探します。  
  
-   自動レジスタ割り当て  
  
     この最適化を行うと、頻繁に使う変数および部分式がレジスタに格納されます。`register` キーワードは無視されます。  
  
-   ループの最適化  
  
     ループを最適化すると、不変の部分式がループ本体から削除されます。  最適化したループには、ループを実行するたびに値が変わる式だけが残ります。  次の例では、式 `x + y` はループ本体の中では変化しません。  
  
    ```  
    i = -100;  
    while( i < 0 ) {  
        i += x + y;  
    }  
    ```  
  
     最適化後は、 `x + y` が 1 回だけ計算されます。つまり、ループが実行されるたびには計算されません。  
  
    ```  
    i = -100;  
    t = x + y;  
    while( i < 0 ) {  
        i += t;  
    }  
    ```  
  
     ループの最適化は、エイリアスを使用しないとコンパイラで見なすことができる場合、効率が大幅に向上します。エイリアスの有無は、[\_\_restrict](../../cpp/extension-restrict.md)、[noalias](../../cpp/noalias.md)、または [restrict](../../cpp/restrict.md) で設定します。  
  
    > [!NOTE]
    >  `optimize`  プラグマに `g` オプションを指定すると、グローバルな最適化の有効\/無効を関数ごとに切り替えることができます。  
  
 **\/Og** では、名前付き戻り値の最適化も有効になります。この最適化では、スタック ベースの戻り値のコンストラクターとデストラクターがコピーされません。  詳細については、「[\/O1、\/O2 \(プログラム サイズ、実行速度\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)」を参照してください。  
  
 関連情報については、「[\/Oi \(組み込み関数の生成\)](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md)」、および「[\/Ox \(最大限の最適化\)](../../build/reference/ox-full-optimization.md)」を参照してください。  
  
 **\/Og** は使用されていません。代わりに [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) または **\/O2** を使用してください。  詳細については、「[Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ja-jp/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [\/O オプション \(コードの最適化\)](../../build/reference/o-options-optimize-code.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)