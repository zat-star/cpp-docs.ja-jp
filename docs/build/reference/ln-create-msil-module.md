---
title: "-LN (MSIL モジュールの作成) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /LN
dev_langs: C++
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0278d59af9a62393f90a91655e3d7f0323e08118
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ln-create-msil-module"></a>/LN (MSIL モジュールの作成)
アセンブリ マニフェストを出力ファイルに挿入できないことを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/LN  
```  
  
## <a name="remarks"></a>コメント  
 既定では、 **/LN**は無効 (アセンブリ マニフェストを出力ファイルに挿入します)。  
  
 ときに**/LN**を使用するのいずれか、 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)オプションが使用することも必要があります。  
  
 マニフェスト内にアセンブリ メタデータがないマネージ プログラムには、モジュールが呼び出されます。 コンパイルする場合[(コンパイルなしのリンク)/c](../../build/reference/c-compile-without-linking.md)と**/LN**、指定[/NOASSEMBLY (MSIL モジュールの作成)](../../build/reference/noassembly-create-a-msil-module.md)フェーズでは、リンカー出力ファイルを作成します。  
  
 アセンブリをビルドするため、コンポーネント ベースのアプローチを実行する場合、モジュールを作成することがあります。  つまり、型を作成し、モジュールにコンパイルできます。  次に、1 つまたは複数のモジュールからアセンブリを生成することができます。  モジュールからアセンブリを作成する方法の詳細については、次を参照してください。[リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)または[Al.exe (アセンブリ リンカー)](/dotnet/framework/tools/al-exe-assembly-linker)です。  
  
 モジュールの既定のファイル拡張子は、.netmodule です。  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] Visual C 2005 以前のリリースで作成された、モジュール**/clr:noAssembly**です。  
  
 Visual C リンカーは、入力として .netmodule ファイルを受け入れるし、アセンブリまたは .netmodule ない実行時の依存をリンカー入力した .netmodule のいずれかのリンカーによって生成される出力ファイルが表示されます。  詳細については、「 [リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)」を参照してください。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
-   指定[/NOASSEMBLY (MSIL モジュールの作成)](../../build/reference/noassembly-create-a-msil-module.md)フェーズでは、リンカー出力ファイルを作成します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   このコンパイラ オプションをプログラムで変更できません。  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)