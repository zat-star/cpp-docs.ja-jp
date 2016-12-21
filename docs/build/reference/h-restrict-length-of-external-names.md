---
title: "/H (外部名の長さの制限) | Microsoft Docs"
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
  - "/h"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/H コンパイラ オプション [C++]"
  - "外部名"
  - "H コンパイラ オプション [C++]"
  - "-H コンパイラ オプション [C++]"
  - "パブリック名の長さ"
ms.assetid: de701dd3-ed04-4c88-8195-960d2520ec2e
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /H (外部名の長さの制限)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

外部名の長さを制限します。  
  
## 構文  
  
```  
/Hnumber  
```  
  
## Arguments  
 `number`  
 プログラムで許可された外部名の長さの最大値を指定します。  
  
## 解説  
 既定では、外部 \(パブリック\) 名の長さは 2,047 文字です。  これは C および C\+\+ のプログラムにも当てはまります。  **\/H** では、識別子の最大許容長を短くできますが、長くはできません。  **\/H** と `number` の間にはスペースを挿入してもかまいません。  
  
 プログラムに、`number` を超える文字数の外部名が含まれていると、超過分の文字は無視されます。  **\/H** を使わずにプログラムをコンパイルし、識別子が 2,047 文字を超えると、コンパイラは [致命的なエラー C1064](../Topic/Fatal%20Error%20C1064.md) を生成します。  
  
 コンパイラが名前の先頭に付加したアンダースコア \(\_\) やアット マーク \(@\) も文字として数えられます。  これらの文字は識別子の一部であり、意味のある位置に付加されます。  
  
-   名前の先頭にアンダースコアが付加されるのは、`__cdecl` 呼び出し規約 \(既定\) または `__stdcall` 呼び出し規約で名前を修飾した場合です。これに対し、名前の先頭にアット マークが付加されるのは、`__fastcall` 呼び出し規約で名前を修飾した場合です。  
  
-   `__fastcall` 呼び出し規約や `__stdcall` 呼び出し規約で修飾された名前には引数のサイズ情報が付加されます。C\+\+ の名前には型情報が付加されます。  
  
 **\/H** は以下の場合に便利です。  
  
-   複数の言語を使用したプログラムや移植性の高いプログラムを作成するとき。  
  
-   外部識別子の長さを制限しているツールを使用するとき。  
  
-   デバッグ ビルドでシンボルに使用する領域を制限するとき。  
  
 識別子の長さを制限しすぎた場合に、**\/H** の使用によって実際にどのようなエラーが発生するのかを次の例に示します。  
  
```  
// compiler_option_H.cpp  
// compile with: /H5  
// processor: x86  
// LNK2005 expected  
void func1(void);  
void func2(void);  
  
int main() { func1(); }  
  
void func1(void) {}  
void func2(void) {}  
```  
  
 また、**\/H** オプションを使用するときは、コンパイラの定義済みの識別子にも注意してください。  識別子の最大長が小さすぎると、一部の定義済み識別子やライブラリ関数呼び出しを解決できなくなります。  たとえば、`printf` 関数を使用する場合は、コンパイル時に **\/H5** オプションが指定されていると、`printf` を参照するためにシンボル **\_prin** が作成されますが、これをライブラリで見つけることができなくなります。  
  
 **\/H** を [\/GL \(プログラム全体の最適化\)](../../build/reference/gl-whole-program-optimization.md) と併用することはできません。  
  
 **\/H** は使用しないでください。最大長の上限が引き上げられたので、**\/H** は必要なくなりました。詳細については、「[Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ja-jp/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  \[追加のオプション\]ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)