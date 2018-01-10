---
title: "-await (コルーチン サポートを有効にする) |Microsoft ドキュメント"
ms.custom: 
ms.date: 08/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /await
- -await
dev_langs: C++
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 47134532b16d1b5a907e4ed3170a0827316d7c65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="await-enable-coroutine-support"></a>/await (コルーチン サポートを有効にする)  
  
使用して、 **/await**コルーチンのコンパイラ サポートを有効にするコンパイラ オプション。  
  
## <a name="syntax"></a>構文  
  
> /await  
  
## <a name="remarks"></a>コメント  
  
**/Await**コンパイラ オプションを有効に C++ コルーチンとキーワードのコンパイラ サポート**co_await**、 **co_yield**、および**co_return**. このオプションの既定値はオフです。 Visual Studio でのコルーチンのサポートについては、次を参照してください。、 [Visual Studio チームのブログ](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/)です。 コルーチンの標準提案の詳細については、次を参照してください。 [N4628 作業下書き、コルーチンの C++ の拡張機能の技術仕様](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/n4628.pdf)です。  

**/Await**オプションは、Visual Studio 2015 以降を使用できます。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1. プロジェクトの開く**プロパティ ページ** ダイアログ ボックス。   
  
2. **構成プロパティ**、展開、 **C/C++**フォルダーを選択し、**コマンド ライン**プロパティ ページ。  
  
3. 入力、 **/await**コンパイラ オプション、**追加オプション**ボックス。 選択**OK**または**適用**して変更を保存します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
  
[コンパイラ オプション](../../build/reference/compiler-options.md)   
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)