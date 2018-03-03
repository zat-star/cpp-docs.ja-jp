---
title: "-hotpatch (ホットパッチ可能なイメージの作成) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
dev_langs:
- C++
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad7ab4e6450d33923b728f20c8a35185edd2b05e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch (ホットパッチ可能なイメージの作成)
イメージをホットパッチできるようにします。  
  
## <a name="syntax"></a>構文  
  
```  
/hotpatch  
```  
  
## <a name="remarks"></a>コメント  
 ときに**/hotpatch**使用は、コンパイル時に、コンパイラは、確認の各関数の最初の命令がホットパッチに必要な 2 バイト以上であります。  
  
 使用した後、イメージ ホットパッチ可能なを行うための準備を完了する**/hotpatch**使用する必要がありますをコンパイルする[/FUNCTIONPADMIN (ホットパッチ可能なイメージの作成)](../../build/reference/functionpadmin-create-hotpatchable-image.md)にリンクします。 コンパイルの cl.exe、1 つの呼び出しを使用してイメージをリンクすると**/hotpatch**意味**/functionpadmin**です。  
  
 命令は 2 バイトでは常にあるため、ARM アーキテクチャでより大きいか、x64 コンパイルは常に扱われますかのよう**/hotpatch**が指定されている、指定する必要はありません**/hotpatch**ときにこれらのターゲットをコンパイルします。ただし、する必要がありますしてリンクを使用して**/functionpadmin**をそれらのホットパッチ可能なイメージを作成します。 **/Hotpatch**コンパイラ オプションのみに影響 x86 コンパイルします。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、 **C/C++**フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  コンパイラ オプションを追加、**追加オプション**ボックス。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="guidance"></a>ガイダンス  
 更新管理の詳細についてを参照してください「管理用の更新されたセキュリティ ガイダンス」 [http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx](http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx)です。  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)