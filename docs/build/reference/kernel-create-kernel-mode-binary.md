---
title: "/kernel (カーネル モード バイナリの作成) | Microsoft Docs"
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
  - "/kernel"
  - "/kernel-"
dev_langs: 
  - "C++"
ms.assetid: 6d7fdff0-c3d1-4b78-9367-4da588ce8b05
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /kernel (カーネル モード バイナリの作成)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows のカーネルで実行できるバイナリを作成します。  
  
## 構文  
  
```  
/kernel[-]  
```  
  
## Arguments  
 **\/kernel**  
 現在のプロジェクト内のコードがコンパイルされ、一連の値をコードに固有の C\+\+ 言語の規則を使用して、リンクされたカーネル モードで実行されます。  
  
 **\/kernel\-**  
 現在のプロジェクト内のコードがコンパイルされ、それをコードに固有の C\+\+ 言語規則を使用せずにリンクされるカーネル モードで実行されます。  
  
## 解説  
 `#pragma` には、このオプションを制御するための相当するものはありません。  
  
 **\/kernel** オプションを指定すると、コンパイラとリンカーをどの言語機能がカーネル モードで System.Runtime.InteropServices.SafeHandle.ReleaseHandle、カーネル モード C\+\+ 固有の実行時間が不安定な状態を回避するための十分な表現力が確実にまたは仲裁するように指示します。  これは、カーネル モードやリスクがある実行されますが、無効になるできません C\+\+ 言語機能に警告を指定することによって影響を受ける可能性がある C\+\+ 言語機能を使用することによって異なります。  
  
 **\/kernel** オプションはビルドのコンパイラとリンカー フェーズの両方に適用され、プロジェクト レベルで設定されます。  リンク時に、そのバイナリが Windows カーネルに読み込まれることを示します **\/kernel** をに切り替えますコンパイラに渡します。  コンパイラは、カーネルと互換性のあるサブセットに C\+\+ 言語機能の範囲を限定できます。  
  
 次の表は **\/kernel** を指定した場合、コンパイラの動作の変更点を示します。  
  
|動作の種類|**\/kernel** の 動作|  
|-----------|-----------------------|  
|C\+\+ Exception Handling|無効。  `throw` と `try` キーワードのすべてのインスタンスはコンパイラ エラーを生成します \(例外指定 `throw()`を除く\)。  **\/EH** オプションは **\/EH\-**を除く **\/kernel**と互換性がありません。|  
|RTTI|無効。  `dynamic_cast` と `typeid` キーワードのすべてのインスタンスが `dynamic_cast` が静的に使用されていない場合は、コンパイラ エラーが発生します。|  
|`new` および `delete`|明示的に `new()` または `delete()` の演算子を定義する必要があります。; コンパイラ、ランタイムが既定の定義を確認しません。|  
  
 **\/kernel** オプションを使用するとカスタム呼び出し規約、[\/GS](../Topic/-GS%20\(Buffer%20Security%20Check\).md) のビルド オプションとすべての最適化が割り当てられます。  インライン展開はコンパイラによって有効に対して同じ意味を **\/kernel**に、主として、影響されません。  `__forceinline` のインライン展開修飾子は、優先されるようにするには、点 `__forceinline` 関数にインラインか確認するように [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) に警告することが有効になっていることを確認してください。  
  
 コンパイラが **\/kernel** スイッチに渡された場合、`_KERNEL_MODE` という名前で、値 **1**を持つプリプロセッサ マクロを定義します。  実行環境がユーザー モードまたはカーネル モードかどうかを、条件に基づいてコードをコンパイルするために使用できます。  たとえば、次のコードは、カーネル モードの実行用にコンパイルするとき、クラスがページング不可メモリ セグメントに配置する必要があることを指定します。  
  
```cpp  
#ifdef _KERNEL_MODE  
#define NONPAGESECTION __declspec(code_seg("$kerneltext$"))  
#else  
#define NONPAGESECTION  
#endif  
  
class NONPAGESECTION MyNonPagedClass  
{  
  
};  
  
```  
  
 一部はターゲット アーキテクチャと **\/arch** 次に示すオプションの組み合わせ **\/kernel**で使用するとエラーを生成する:  
  
-   **\/arch:{SSE&#124;SSE2&#124;AVX}** は x86 ではサポートされていません。  **\/arch:IA32** のみ x86 の **\/kernel** がサポートされます。  
  
-   **\/arch:AVX** は x64 の **\/kernel** でサポートされません。  
  
 **\/kernel** のビルドは、リンカーに **\/kernel** を渡します。  これは、リンカーの動作にどのように影響するか Her:  
  
-   インクリメンタル リンクは無効になります。  コマンド ラインに **\/incremental** を追加した場合、リンカーはこの致命的なエラーを生成する:  
  
     **LINK : fatal error LNK1295: '\/INCREMENTAL' not compatible with '\/KERNEL' specification; link without '\/INCREMENTAL'**  
  
-   リンカーは、コンパイルされた場合でも、ファイルをチェック アウトし **\/kernel** オプションを使用することで、そうでないかどうかを参照するように各オブジェクト ファイル \(またはスタティック ライブラリのインクルード アーカイブのメンバーを\)。  各インスタンスは、この条件を満たしていれば、正常にまだリンカー リンクを次の表に示すように、警告を生成する場合があります。  
  
    ||**\/kernel** obj|**\/kernel\-** obj、MASM obj、または cvtresed|**\/kernel** と **\/kernel\-** の objs のミックス|  
    |-|----------------------|----------------------------------------------|------------------------------------------------|  
    |**LINK \/kernel**|Yes|Yes|はいを LNK4257 の警告と|  
    |**link**|Yes|Yes|Yes|  
  
     **LNK4257 linking object not compiled with \/KERNEL ; image may not run**  
  
 **\/kernel** オプションと **\/driver** オプションと、他の影響は独立して動作しません。  
  
### Visual Studio で \/kernel コンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  **\[追加のオプション\]** ボックスで、`/kernel` または `/kernel-`を追加します。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)