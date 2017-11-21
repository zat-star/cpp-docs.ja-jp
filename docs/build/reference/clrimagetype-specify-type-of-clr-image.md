---
title: "-CLRIMAGETYPE (CLR イメージの種類の指定) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
dev_langs: C++
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6f11684f71e874d2dbb439ed1f9dfc46b543a63e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (CLR イメージのタイプの指定)
```  
/CLRIMAGETYPE:{IJW|PURE|SAFE|SAFE32BITPREFERRED}  
```  
  
## <a name="remarks"></a>コメント  
 リンカーは、ネイティブ オブジェクトを受け取り、MSIL オブジェクトを使用してコンパイルされるも[/clr](../../build/reference/clr-common-language-runtime-compilation.md)/clr: 純粋、または/clr:safe です。 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。 同じビルドに混在するオブジェクトを渡すと、生成される出力ファイルの検証可能性は、既定で入力モジュールの最低レベルの検証可能性と等しくなります。 たとえば、安全で純粋なモジュールをリンカーに渡した場合は、出力ファイルは純粋になります。 ネイティブ イメージと混合モード イメージを渡す場合 (を使用してコンパイル**/clr**)、結果のイメージは混合モード イメージになります。  
  
 /CLRIMAGETYPE を使用すると、必要に応じてより低い検証可能性を指定できます。  
  
 .NET 4.5 では、/CLRIMAGETYPE は SAFE32BITPREFERRED オプションをサポートします。 これにより、(イメージの PE ヘッダーに) MSIL オブジェクトは安全ですべてのプラットフォームで実行可能であるが、32 ビットの実行環境が推奨されることを示すフラグが設定されます。 このオプションにより、アプリを ARM プラットフォームで実行することが可能になるほか、64 ビットの実行環境を使用する代わりに、64 ビット オペレーティング システムの WOW64 で実行するように指定することができます。  
  
 使用してコンパイルされた .exe **/clr**または**/clr: 純粋な**実行は wow64 で 32 ビット アプリケーションが 64 ビット オペレーティング システムで実行できるように、アプリケーションを実行する 64 ビット オペレーティング システムでは、上。 既定を使用してコンパイルされた .exe **/clr:safe**オペレーティング システムの 64 ビット サポートで実行します。 ただし、お使いの安全なアプリケーションで 32 ビット コンポーネントを読み込むことができます。 この場合、オペレーティング システムの 64 ビット サポートで実行している安全なイメージで 32 ビット アプリケーションを読み込もうとすると失敗します。 安全なイメージが 64 ビット オペレーティング システムで 32 ビット コンポーネントを読み込むときに、そのイメージを引き続き安全に実行するためには、/CLRIMAGETYPE:SAFE32BITPREFERRED オプションを使用します。 コードを ARM プラットフォームで実行する必要がない場合は、/CLRIMAGETYPE:PURE オプションを指定して、WOW64 で実行されるように (および独自のエントリ シンボルに置き換えるように) メタデータ (.corflags) を変更できます。  
  
 **cl /clr:safe t.cpp /link /clrimagetype:pure /entry:?main@@$$HYMHXZ /subsystem:console**  
  
 ファイルの CLR イメージのタイプを判断する方法については、「 [/CLRHEADER](../../build/reference/clrheader.md)」を参照してください。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**詳細**プロパティ ページ。  
  
5.  変更、 **CLR イメージ タイプ**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)