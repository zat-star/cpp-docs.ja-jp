---
title: "-Zc: インライン (参照されない COMDAT の除去) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Zc:inline
- VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
- /Zc:inline
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c8d14f6055c96f5c9feed16d2ad0b996f0d0b94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline (参照されない COMDAT の除去)
COMDAT であるか内部リンケージのみを持つ、参照されていない関数またはデータを削除します。 ときに**/Zc:inline**を指定すると、コンパイラは、インライン データまたはインライン関数を使用する翻訳単位でのデータまたは関数の定義する必要がありますも含まれることが必要です。  
  
## <a name="syntax"></a>構文  
  
```  
/Zc:inline[-]  
```  
  
## <a name="remarks"></a>コメント  
 ときに**/Zc:inline**を指定すると、コンパイラが参照されていない COMDAT 関数またはデータ、または関数または内部リンケージのみを持つデータのシンボル情報を生成しません。 既定では、このオプションはオフ (**/Zc:inline-**)。 この最適化はリリース ビルドでは、リンカーによって実行される作業の一部を簡略化またはリンカー オプション[/opt:ref による](../../build/reference/opt-optimizations.md)を指定します。 コンパイラによってこの最適化が実行されると、.obj ファイルのサイズを大幅に縮小し、リンカーの速度を向上させることができます。 このコンパイラ オプションが有効になっていません最適化が無効にした場合 ([/Od](../../build/reference/od-disable-debug.md)) 場合や[/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)が指定されています。  
  
 場合**/Zc:inline**が指定されている、コンパイラは、c++ 11 の要件のすべての関数が宣言されている`inline`使用される場合、同じ翻訳単位で使用可能な定義を持つ必要があります。 このオプションを指定しない場合、[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] では、定義を参照できなくても `inline` として宣言された関数を起動する非準拠コードが許可されます。 詳細については、C++11 標準のセクション 3.2 およびセクション 7.1.2 を参照してください。 このコンパイラ オプションは、Visual Studio 2013 更新プログラム 2 で導入されました。  
  
 使用する、 **/Zc:inline**オプション、非対応のコードを更新します。 この例は、どのように定義のないインライン関数宣言の非準拠の使用でもコンパイルおよびリンク時に示しています。 既定値**/Zc:inline-**オプションを使用します。  
  
```cpp  
// example.h  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#pragma once  
  
class Example {  
public:  
   inline void inline_call(); // declared but not defined inline  
   void normal_call();  
   Example() {};  
};  
```  
  
```cpp  
// example.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#include <stdio.h>  
#include "example.h"  
  
void Example::inline_call() {  
   printf("inline_call was called.\n");   
}  
  
void Example::normal_call() {  
   printf("normal_call was called.\n");   
   inline_call(); // with /Zc:inline-, inline_call forced into .obj file  
}  
```  
  
```cpp  
// zcinline.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#include "example.h"  
  
void main() {  
   Example example;  
   example.inline_call(); // normal call when definition unavailable  
}  
```  
  
 ときに**/Zc:inline**が有効になって、同じコード、 [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)エラー、コンパイラが、非インライン コードの本体を生成しませんので`Example::inline_call`example.obj 内です。これにより、`main` 内のインライン展開されていない呼び出しは、定義されていない外部シンボルを参照します。  
  
 このエラーを解決するには、`inline` キーワードを `Example::inline_call` の宣言から削除するか、`Example::inline_call` の定義をヘッダー ファイルに移動するか、`Example` の実装を main.cpp に移動します。 次の例では、定義をヘッダー ファイルに移動します。そこでは、ヘッダーを含む任意の呼び出し元から定義を参照できます。  
  
```cpp  
// example2.h  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#pragma once  
#include <stdio.h>  
  
class Example2 {  
public:  
   inline void inline_call() {  
      printf("inline_call was called.\n");   
   }  
   void normal_call();  
   Example2() {};  
};  
```  
  
```cpp  
// example2.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#include "example2.h"  
  
void Example2::normal_call() {  
   printf("normal_call was called.\n");   
   inline_call();   
}  
```  
  
```cpp  
// zcinline2.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#include "example2.h"  
  
void main() {  
   Example2 example2;  
   example2.inline_call(); // normal call when definition unavailable  
}  
```  
  
 Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、 **C/C++**フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  変更、**追加オプション**含めるプロパティを`/Zc:inline`を選択し**OK**です。  
  
## <a name="see-also"></a>参照  
 [/Zc (準拠)](../../build/reference/zc-conformance.md)