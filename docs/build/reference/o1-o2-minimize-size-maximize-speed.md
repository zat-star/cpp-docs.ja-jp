---
title: "/O1、/O2 (プログラム サイズ、実行速度) | Microsoft Docs"
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
  - "/o2"
  - "/o1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/O1 コンパイラ オプション [C++]"
  - "/O2 コンパイラ オプション [C++]"
  - "高速コード"
  - "実行速度コンパイラ オプション [C++]"
  - "プログラム サイズ コンパイラ オプション [C++]"
  - "O1 コンパイラ オプション [C++]"
  - "-O1 コンパイラ オプション [C++]"
  - "O2 コンパイラ オプション [C++]"
  - "-O2 コンパイラ オプション [C++]"
  - "小さいコード"
ms.assetid: 2d1423f5-53d9-44da-8908-b33a351656c2
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /O1、/O2 (プログラム サイズ、実行速度)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルのサイズおよび速度に影響を与える、定義済みのオプション セットを選択します。  
  
## 構文  
  
```  
/O1  
/O2  
```  
  
## 解説  
 **\/O1** および **\/O2** について次の表で説明します。  
  
|オプション|等価オプション|コメント|  
|-----------|-------------|----------|  
|**\/O1** \(最小サイズ\)|**\/Og \/Os \/Oy \/Ob2 \/Gs \/GF \/Gy**|ほとんどの場合、最小サイズのコードを作成します。|  
|**\/O2** \(最高速度\)|**\/Og \/Oi \/Ot \/Oy \/Ob2 \/Gs \/GF \/Gy**|ほとんどの場合、最高速のコードを作成します。これは、リリース ビルドの既定の設定です。|  
  
 **\/O1** と **\/O2** を選択すると、名前付き戻り値の最適化も有効になります。この最適化では、スタック ベースの戻り値のコンストラクターとデストラクターがコピーされません。  次のサンプルを例に取ります。`Test` 関数はコンストラクターまたはデストラクターのコピーを作成しません。  プログラムを実行すると、名前付き戻り値の最適化の効果を参照するには、コンストラクター、デストラクター、およびコピー コンストラクターに出力ステートメントを追加します。  詳細については、参照します [Visual C\+\+ 2005 の名前付きな戻り値の最適化](http://go.microsoft.com/fwlink/?linkid=131571)。  
  
```  
// O1_O2_NRVO.cpp  
// compile with: /O1  
struct A {  
   A() {}  
   ~A() {}  
   A(const A& aa) {}  
};  
  
A Test() {  
   A a;  
   return a;  
}  
int main() {  
   A aa;  
   aa = Test();  
}  
```  
  
 **x86 固有の仕様→**  
  
 これらのオプションでは、[\/Oy](../../build/reference/oy-frame-pointer-omission.md) \(フレーム ポインターの省略\) オプションを暗黙で使うことになります。  
  
 **← x86 固有の仕様**  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[最適化\]** プロパティ ページをクリックします。  
  
4.  **\[最適化\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>」を参照してください。  
  
## 参照  
 [\/O オプション \(コードの最適化\)](../../build/reference/o-options-optimize-code.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [\/EH \(例外処理モデル\)](../../build/reference/eh-exception-handling-model.md)