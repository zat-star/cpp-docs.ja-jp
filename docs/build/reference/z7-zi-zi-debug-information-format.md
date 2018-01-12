---
title: "-Z7、-zi、ZI (デバッグ情報の形式) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.DebugInformationFormat
- /zi
- /z7
- VC.Project.VCCLWCECompilerTool.DebugInformationFormat
dev_langs: C++
helpviewer_keywords:
- C7 compatible compiler option [C++]
- -Zl compiler option [C++]
- Debug Information Format compiler option
- ZI compiler option
- -Zi compiler option [C++]
- /ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debug information files
- Zi compiler option [C++]
- none compiler option [C++]
- /Zi compiler option [C++]
- program database compiler option [C++]
- full symbolic debugging information
- /Z7 compiler option [C++]
- line numbers only compiler option [C++]
- cl.exe compiler, debugging options
- -Z7 compiler option [C++]
ms.assetid: ce9fa7e1-0c9b-47e3-98ea-26d1a16257c8
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0b80339192a7d335b0989ac8a67446c0f5716a76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7、/Zi、/ZI (デバッグ情報の形式)
作成するプログラムに対して生成するデバッグ情報の種類を選択し、デバッグ情報をオブジェクト (.obj) ファイルに保存するのかプログラム データベース (PDB) に保存するのかを選択します。  
  
## <a name="syntax"></a>構文  
  
```  
/Z{7|i|I}  
```  
  
## <a name="remarks"></a>コメント  
 これらのオプションの説明を次の表に示します。  
  
 なし  
 デバッグ情報を生成しないため、コンパイルが高速化されます。  
  
 **/Z7**  
 デバッガーで使用される詳細なシンボリック デバッグ情報が含まれた .obj ファイルが作成されます。 シンボリック デバッグ情報には、変数や関数の名前と型、および行番号が含まれます。 .pdb ファイルは作成されません。  
  
 サードパーティのライブラリを配布する場合は、.pdb ファイルを持たないことによる利点があります。 ただし、プリコンパイル済みヘッダーの .obj ファイルは、リンク フェーズおよびデバッグで必要です。 型情報だけ (コードを含まない) .pch オブジェクト ファイルの場合は、使用してコンパイルする必要が[/Yl (挿入 PCH 参照デバッグ ライブラリの)](../../build/reference/yl-inject-pch-reference-for-debug-library.md)です。  
  
 **/Zi**  
 プログラム データベース (PDB) が生成されます。PDB には、型情報とデバッガーが使うシンボリック デバッグ情報が取り込まれます。 シンボリック デバッグ情報には、変数や関数の名前と型、および行番号が含まれます。  
  
 **/Zi**の最適化には影響しません。 ただし、 **/Zi**わけでは**/debug**; を参照してください[/DEBUG (デバッグ情報の生成)](../../build/reference/debug-generate-debug-info.md)詳細についてはします。  
  
 型情報は、.obj ファイルではなく .pdb ファイルに配置されます。  
  
 使用することができます[/Gm (簡易リビルドの有効)](../../build/reference/gm-enable-minimal-rebuild.md)で**/Zi**であるのに対し**/gm 化**でコンパイルする場合は使用できません**/Z7**です。  
  
 コンパイルするときに**/Zi**と**/clr**、<xref:System.Diagnostics.DebuggableAttribute>属性がアセンブリのメタデータに配置できません以外の場合は、ソース コードで指定する必要があります。 この属性は、アプリケーションの実行時パフォーマンスに影響します。 デバッグ可能な属性がパフォーマンスに与える影響し、パフォーマンスに与える影響を変更する方法の詳細については、次を参照してください。[デバッグするイメージの簡略化を行う](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug)です。  
  
 **/ZI**  
 エディット コンティニュ機能をサポートする形式で、上のようなプログラム データベースを生成します。 エディット コンティニュのデバッグを使用する場合は、必ずこのオプションを使用してください。 ほとんどの最適化にエディット コンティニュと互換性がないために使用**/ZI**も無効になります`#pragma optimize`コードのステートメント。  
  
 **/ZI**により[/Gy (関数レベルのリンクを有効にする)](../../build/reference/gy-enable-function-level-linking.md)と[/FC (完全パスのソース コード ファイルで診断)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md)コンパイル時に使用します。  
  
 **/ZI**と互換性がありません[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)です。  
  
> [!NOTE]
>  **/ZI**はでのみ使用 x86 および x64 プロセッサを対象とすると、コンパイラは、このコンパイラ オプションは ARM プロセッサを対象とすると、コンパイラで使用できます。  
  
 プログラム データベースの名前をコンパイラ*プロジェクト*.pdb です。 プロジェクトにファイルをコンパイルする場合、コンパイラが VC という名前のデータベースを作成*x*0. pdb 場所*x*のメジャー バージョン[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]で使用します。 このオプションを指定して生成した各 .obj ファイルには、PDB の名前が埋め込まれ、シンボル情報と行番号情報の場所がデバッガーに通知されます。 このオプションを選択すると、デバッグ情報は .obj ファイルではなく .pdb ファイルに保存されるため、.obj ファイルのサイズが小さくなります。  
  
 このオプションを使って生成したオブジェクトからライブラリを作成する場合は、ライブラリをプログラムにリンクするときに該当する .pdb ファイルが必要になります。 したがって、ライブラリを配布する場合は、その PDB も併せて配布する必要があります。  
  
 .Pdb ファイルを使用せずにデバッグ情報を含むライブラリを作成するには、コンパイラの C 7.0 互換を選択する必要があります (**/Z7**) オプション。 プリコンパイル済みヘッダー用のオプションを使うと、プリコンパイル済みヘッダーのデバッグ情報は、その他のソース コードのデバッグ情報と共に PDB に保存されます。 **/Yd への取り込み**プログラム データベース オプションを指定するオプションは無視されます。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**全般**プロパティ ページ。  
  
4.  変更、**デバッグ情報の形式**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)