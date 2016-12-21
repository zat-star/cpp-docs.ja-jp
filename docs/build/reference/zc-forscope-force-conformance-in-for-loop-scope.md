---
title: "/Zc:forScope (for ループのスコープの強制準拠) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.ForceConformanceInForLoopScope"
  - "VC.Project.VCCLWCECompilerTool.ForceConformanceInForLoopScope"
  - "/zc:forScope"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc コンパイラ オプション [C++]"
  - "準拠コンパイラ オプション"
  - "Zc コンパイラ オプション [C++]"
  - "-Zc コンパイラ オプション [C++]"
ms.assetid: 3031f02d-3b14-4ad0-869e-22b0110c3aed
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:forScope (for ループのスコープの強制準拠)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft の拡張機能 \([\/Ze](../../cpp/for-statement-cpp.md)\) の[for](../../build/reference/za-ze-disable-language-extensions.md) ループの標準 C\+\+ 動作を実装するために使用します。**\/Zc:forScope** は既定でオンになります。  
  
## 構文  
  
```  
/Zc:forScope[-]  
```  
  
## 解説  
 **\/Zc:forScope\-** オプションは使用されなくなりました。今後のバージョンからは削除されます。**\/Zc:forScope\-** を使うと、廃止予定の警告 D9035 が表示されます。  
  
 標準動作とは、**for** ループの初期化子が **for** ループの後にスコープ外に出るようにすることです。**\/Zc:forScope\-** と [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) では、**for** ループの初期化子は、ローカル スコープが終わるまでスコープ内にとどまります。  
  
 次のコードは **\/Ze** ではコンパイルされますが、**\/Za** ではコンパイルされません。  
  
```cpp  
// zc_forScope.cpp  
// compile by using: cl /Zc:forScope- /Za zc_forScope.cpp  
// C2065, D9035 expected  
int main() {  
    // Compile by using cl /Zc:forScope- zc_forScope.cpp  
    // to compile this non-standard code as-is.  
    // Uncomment the following line to resolve C2065 for /Za.  
    // int i;  
    for (int i = 0; i < 1; i++)  
        ;  
    i = 20;   // i has already gone out of scope under /Za  
}  
```  
  
 **\/Zc:forScope\-** を使う場合、以前のスコープで行った宣言によって変数がスコープ内にあるときに、警告 C4288 \(既定ではオフ\) が表示されます。 これを示すために、サンプル コードから `//` の文字を削除して `int i` を宣言します。  
  
 **\/Zc:forScope** の実行時の動作は、[conform](../../preprocessor/conform.md) プラグマを使って変更できます。  
  
 既存の .pch ファイルがあるプロジェクトで **\/Zc:forScope\-** を使う場合、警告が表示され、**\/Zc:forScope\-** は無視され、既存の .pch ファイルを使ってコンパイルが継続されます。 新しい .pch ファイルを生成する場合、[\/Yc \(プリコンパイル済みヘッダー ファイルの作成\)](../../build/reference/yc-create-precompiled-header-file.md) を使います。  
  
 Visual C\+\+ の準拠に関する問題について詳しくは、「[非標準動作](../Topic/Nonstandard%20Behavior.md)」をご覧ください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  ナビゲーション ウィンドウで、**\[構成プロパティ\]**、**\[C\/C\+\+\]**、**\[言語\]** プロパティ ページを開きます。  
  
3.  **\[for ループ スコープの強制準拠\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope%2A>」を参照してください。  
  
## 参照  
 [\/Zc \(準拠\)](../../build/reference/zc-conformance.md)   
 [\/Za、\/Ze \(言語拡張機能の無効化\)](../../build/reference/za-ze-disable-language-extensions.md)