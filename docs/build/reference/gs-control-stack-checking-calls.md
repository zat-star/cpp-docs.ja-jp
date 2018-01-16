---
title: "-Gs (コントロール スタック チェック呼び出しの) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /GS
dev_langs: C++
helpviewer_keywords:
- disabling stack probes
- GS compiler option [C++]
- /GS compiler option [C++]
- stack, stack probes
- stack probes
- -GS compiler option [C++]
- stack checking calls
ms.assetid: 40daed7c-f942-4085-b872-01e12b37729e
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff02465b4e1b1a727a2367c8d5e038f30854ecc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="gs-control-stack-checking-calls"></a>/Gs (スタック チェック呼び出しの制御)
スタック プローブを制御します。  
  
## <a name="syntax"></a>構文  
  
```  
/Gs[size]  
```  
  
## <a name="arguments"></a>引数  
 `size`  
 (オプション) スタック プローブが開始される前にローカル変数が占有することのできるバイト数。 場合、 **/Gs**オプションを指定することがなく、`size`引数を指定することと同じである**/Gs0**、  
  
## <a name="remarks"></a>コメント  
 スタック プローブとは、コンパイラがすべての関数呼び出しに挿入するコードのシーケンスのことです。 スタック プローブを開始すると、関数のローカル変数を保存するのに必要なスペースの量に応じてメモリに作用します。  
  
 関数でローカル変数用に `size` バイトを超えるスタック領域が必要な場合、スタック プローブが開始されます。 既定で、関数に 1 ページを超えるスタック領域が必要な場合、コンパイラはスタック プローブを開始するコードを生成します。 これは、コンパイラ オプションに相当**/Gs4096** x86、 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]、および ARM プラットフォームです。 この値により、アプリケーションと Windows メモリ マネージャーは、実行時に動的にプログラム スタックにコミットされるメモリの量を増やすことができます。  
  
> [!NOTE]
>  既定値の**/Gs4096**により、実行時に正常に増加するために windows アプリケーションのプログラム スタック。 既定値は、変更理由が明確でない限り変えないことをお勧めします。  
  
 仮想デバイス ドライバーなど一部のプログラムでは、この既定のスタック増加メカニズムは必要ありません。 そのような場合、スタック プローブは必要ではありません。コンパイラがそれらを生成しないようにするには、ローカル変数ストレージでどの関数が必要とする値よりも `size` の値を大きく設定します。 間にスペースは入れません**/Gs**と`size`です。  
  
 **/Gs0**ローカル変数のストレージを必要とされるすべての関数呼び出しに対して、スタック プローブをアクティブにします。 これはパフォーマンスに対して悪影響を及ぼす可能性があります。  
  
 使用して、オンまたはオフ、スタック プローブを有効にすることができます[check_stack](../../preprocessor/check-stack.md)です。 **/Gs**と`check_stack`プラグマは標準 C ライブラリ ルーチンに影響を持ちません。 コンパイルする関数のみに影響します。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、 **C/C++**フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)