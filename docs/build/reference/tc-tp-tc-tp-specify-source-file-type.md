---
title: "-Tc、-tp、-/TC、-TP (ソース ファイルの種類の指定) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
dev_langs: C++
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
ms.assetid: 7d9d0a65-338b-427c-8b48-fff30e2f9d2b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 69ccd08967d386780744fb85476033430127ba3a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc、/Tp、/TC、/TP (ソース ファイル タイプの指定)
**/Tc**オプションを指定する`filename`C ソース ファイルを .c という拡張子があるない場合でもはします。 **/Tp**オプションを指定する`filename`.cpp または .cxx 拡張子を持たない場合でも、C++ ソース ファイルがします。 オプションの間にスペースと`filename`は省略可能です。 各オプションを 1 つのファイルを指定します追加のファイルを指定するには、オプションを繰り返します。  
  
 **/TC**と**/TP**のグローバルのバリアントは、 **/Tc**と**/Tp**です。 コンパイラが C ソース ファイルとして名前をコマンドラインですべてのファイルを扱うため (**/TC**) または C++ ソース ファイル (**/TP**)、コマンド ライン オプションに関連して上の場所に関係なく。 これらのグローバル オプションの 1 つのファイルでオーバーライドできます**/Tc**または**/Tp**です。  
  
## <a name="syntax"></a>構文  
  
```  
/Tcfilename  
/Tpfilename  
/TC  
/TP  
```  
  
## <a name="arguments"></a>引数  
 `filename`  
 C または C++ ソース ファイル。  
  
## <a name="remarks"></a>コメント  
 既定では、CL には、.c ファイル拡張子を持つファイルは、C ソース ファイルと .cpp または .cxx 拡張子を持つファイルがある C++ ソース ファイルがあると想定します。  
  
 ときにいずれか、 **TC**または**Tc**オプションを指定するの任意の仕様、 [/Zc:wchar_t (wchar_t をネイティブ型)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md)オプションは無視されます。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**詳細**プロパティ ページ。  
  
4.  変更、**としてコンパイル**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>」を参照してください。  
  
## <a name="examples"></a>使用例  
 CL の次のコマンドラインでは、MAIN.c、TEST.prg と COLLATE.prg があるすべての C ソース ファイルを指定します。 CL では、PRINT.prg は認識されません。  
  
```  
CL MAIN.C /TcTEST.PRG /TcCOLLATE.PRG PRINT.PRG  
```  
  
 CL の次のコマンドラインを指定 TEST1.c、TEST2.cxx、TEST3.huh、および TEST4.o は、C++ ファイルとしてコンパイル TEST5.z は C ファイルとしてコンパイルします。  
  
```  
CL TEST1.C TEST2.CXX TEST3.HUH TEST4.O /Tc TEST5.Z /TP  
```  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)