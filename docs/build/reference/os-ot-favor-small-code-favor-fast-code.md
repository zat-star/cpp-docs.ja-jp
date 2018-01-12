---
title: "-Os、-ot (コードは、高速コードの実行速度の優先) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed
- /os
- VC.Project.VCCLCompilerTool.FavorSizeOrSpeed
dev_langs: C++
helpviewer_keywords:
- favor fast code compiler option [C++]
- /Os compiler option [C++]
- Ot compiler option [C++]
- /Ot compiler option [C++]
- small machine code
- -Ot compiler option [C++]
- fast code
- favor small code compiler option [C++]
- Os compiler option [C++]
- -Os compiler option [C++]
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 02ce4b7d5c9617a88450fd90b4ac6c75d41148ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>/Os、/Ot (実行可能ファイルのサイズの優先、実行速度の優先)
最小化または Exe および Dll のサイズを最大化します。  
  
## <a name="syntax"></a>構文  
  
```  
/Os  
/Ot  
```  
  
## <a name="remarks"></a>コメント  
 **/Os** (コード) 速度よりサイズを優先するように、コンパイラ、Exe および Dll のサイズを最小化します。 コンパイラは、機能的に同等のマシン語コードの多くの C および C++ コンストラクトを減らすことができます。 場合によってはこれらの相違点は、サイズの速度とのトレードオフを提供します。 **/Os**と**/Ot**オプションを使用すると、他の中の 1 つの基本設定を指定します。  
  
 **/Ot** (優先高速コード) のサイズを超える速度を優先するようにコンパイラに指示して Exe および Dll の速度を最大化します。 (これは、既定値です)。コンパイラは、機能的に同等のマシン語コードの多くの C および C++ コンストラクトを減らすことができます。 場合によっては、これらの相違点は、サイズの速度とのトレードオフを提供します。 /Ot オプションは、最大速度で暗黙的に指定 ([/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)) オプション。 **/O2**オプション非常に高速のコードを生成するためにいくつかのオプションを組み合わせています。  
  
 使用する場合**/Os**または**/Ot**も指定する必要があります、 [/Og](../../build/reference/og-global-optimizations.md)コードを最適化します。  
  
> [!NOTE]
>  プロファイリングのテスト実行から収集される情報を指定する場合に有効なそれ以外の場合になる最適化がオーバーライドされます**/Ob**、 **/Os**、または**/Ot**です。 詳細については、[ガイド付き最適化の](../../build/reference/profile-guided-optimizations.md)します。  
  
 **x86 固有**  
  
 次のコード例は、コードは、違いを示します (**/Os**) オプションと、/os (**/Ot**) オプション。  
  
> [!NOTE]
>  使用する場合、次に、予想される動作について説明します**/Os**または**/Ot**です。 ただし、コンパイラの動作リリースごとに次のコードにさまざまな最適化されない可能性があります。  
  
```  
/* differ.c  
  This program implements a multiplication operator  
  Compile with /Os to implement multiply explicitly as multiply.  
  Compile with /Ot to implement as a series of shift and LEA instructions.  
*/  
int differ(int x)  
{  
    return x * 71;  
}  
```  
  
 以下のマシン語コードのフラグメントに示すように、いつ DIFFER.c がコンパイルされるサイズ (**/Os**)、コンパイラを実装、乗算、return ステートメントの式として明示的に、コードの短いが低速シーケンスを生成するために乗算。  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
imul   eax, 71                  ; 00000047H  
```  
  
 速度の DIFFER.c がコンパイルされたときに代わりに、(**/Ot**)、コンパイラを実装、乗算を一連の shift キーを押し、return ステートメントの式と`LEA`コードの高速であるは長いシーケンスを生成するために手順。  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
mov    ecx, eax  
shl    eax, 3  
lea    eax, DWORD PTR [eax+eax*8]  
sub    eax, ecx  
```  
  
 **END x86 固有**  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**最適化**プロパティ ページ。  
  
4.  変更、**速度またはサイズを優先**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)