---
title: "-Zc: forScope (の強制準拠 for ループ スコープの) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.ForceConformanceInForLoopScope
- VC.Project.VCCLWCECompilerTool.ForceConformanceInForLoopScope
- /zc:forScope
dev_langs:
- C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: 3031f02d-3b14-4ad0-869e-22b0110c3aed
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 243966ae5e8c7d0792f40206adc9d0ae3b2fb673
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="zcforscope-force-conformance-in-for-loop-scope"></a>/Zc:forScope (for ループのスコープの強制準拠)
Microsoft の拡張機能 ( [/Ze](../../cpp/for-statement-cpp.md) ) の[for](../../build/reference/za-ze-disable-language-extensions.md)ループの標準 C++ 動作を実装するために使用します。  **/Zc:forScope** は既定でオンになります。  
  
## <a name="syntax"></a>構文  
  
```  
/Zc:forScope[-]  
```  
  
## <a name="remarks"></a>コメント  
 **/Zc:forScope-** オプションは使用されなくなりました。今後のバージョンからは削除されます。 **/Zc:forScope-** を使うと、廃止予定の警告 D9035 が表示されます。  
  
 標準動作とは、 **for** ループの初期化子が **for** ループの後にスコープ外に出るようにすることです。 **/Zc:forScope-** と [/Ze](../../build/reference/za-ze-disable-language-extensions.md)では、 **for** ループの初期化子は、ローカル スコープが終わるまでスコープ内にとどまります。  
  
 次のコードは **/Ze** ではコンパイルされますが、 **/Za**ではコンパイルされません。  
  
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
  
 **/Zc:forScope-**を使う場合、以前のスコープで行った宣言によって変数がスコープ内にあるときに、警告 C4288 (既定ではオフ) が表示されます。 これを示すために、サンプル コードから `//` の文字を削除して `int i`を宣言します。  
  
 **/Zc:forScope** の実行時の動作は、 [conform](../../preprocessor/conform.md) プラグマを使って変更できます。  
  
 既存の .pch ファイルがあるプロジェクトで **/Zc:forScope-** を使う場合、警告が表示され、 **/Zc:forScope-** は無視され、既存の .pch ファイルを使ってコンパイルが継続されます。 新しい .pch ファイルを生成する場合は、使用[/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)です。  
  
 Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  ナビゲーション ウィンドウで、 **[構成プロパティ]**、 **[C/C++]**、 **[言語]** プロパティ ページを開きます。  
  
3.  **[for ループ スコープの強制準拠]** プロパティを変更します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [/Zc (準拠)](../../build/reference/zc-conformance.md)   
 [/Za、/Ze (言語拡張を無効にする)](../../build/reference/za-ze-disable-language-extensions.md)