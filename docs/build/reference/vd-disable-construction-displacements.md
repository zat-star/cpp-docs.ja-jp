---
title: "/vd (ディスプレイスメントの無効化) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/vd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/vd0 コンパイラ オプション [C++]"
  - "/vd1 コンパイラ オプション [C++]"
  - "/vdn (ディスプレイスメントを無効化する) コンパイラ オプション"
  - "コンストラクターの変位"
  - "無効化 (ディスプレイスメントを) コンパイラ オプション"
  - "displacements コンパイラ オプション"
  - "vd0 コンパイラ オプション [C++]"
  - "-vd0 コンパイラ オプション [C++]"
  - "vd1 コンパイラ オプション [C++]"
  - "-vd1 コンパイラ オプション [C++]"
  - "vtordisp フィールド"
ms.assetid: 93258964-14d7-4b1c-9cbc-d6f4d74eab69
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# /vd (ディスプレイスメントの無効化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
/vdn  
```  
  
## Arguments  
 `0`  
 vtordisp コンストラクター\/デストラクター ディスプレイスメント メンバーを無効にします。  このオプションは、すべてのクラス コンストラクターとデストラクターが仮想的に仮想関数を呼び出すことが確実な場合にだけ、選択してください。  
  
 `1`  
 隠し vtordisp コンストラクター\/デストラクター ディスプレイスメント メンバーの作成を有効にします。  これは、既定の設定です。  
  
 `2`  
 構築中のオブジェクトで [dynamic\_cast 演算子](../../cpp/dynamic-cast-operator.md) を使用できます。  仮想基本クラスから派生クラスへの dynamic\_cast はその一例です。  
  
 **\/vd2** は、仮想関数を持つ仮想基本クラスがあるときに vtordisp フィールドを追加します。  **\/vd1** でも十分です。  **\/vd2** が必要となる最も一般的なケースは、仮想基本クラス内の唯一の仮想関数がデストラクターである場合です。  
  
## 解説  
 次のオプションは、仮想基本クラスを使用する C\+\+ コードだけに適用されます。  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] では、仮想継承に対して C\+\+ ディスプレイスメントをサポートしています。  ディスプレイスメントを使用すると、仮想基本クラスで宣言され、派生クラスでオーバーライドされた仮想関数が、さらに派生したクラスの構築中にコンストラクターから呼び出されたときに発生する問題を解決できます。  
  
 この問題は、基本クラスとその派生クラスとの間で仮想基本クラスの位置が異なるために、不当な `this` ポインターが仮想関数に渡されることが原因です。  この問題を解決するために、各仮想基本クラスに対して vtordisp フィールドと呼ばれる単一のディスプレイスメントがサポートされています。  
  
 既定では、コード内でユーザー定義のコンストラクターとデストラクターの両方が定義され、仮想基本クラスの仮想関数がオーバーライドされている場合は、必ず vtordisp フィールドが挿入されます。  
  
 \/vd*n* オプションは、ソース ファイル全体に反映されます。  [vtordisp](../Topic/vtordisp.md) を使用すると、vtordisp フィールドをクラス単位で無効化したり、再度有効化したりできます。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)