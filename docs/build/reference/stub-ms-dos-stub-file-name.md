---
title: "スタブ (MS-DOS スタブ ファイル名) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /stub
- VC.Project.VCLinkerTool.DosStub
dev_langs:
- C++
helpviewer_keywords:
- Win32 [C++], attaching MS-DOS stub program
- STUB linker option
- MS-DOS stub file name linker option
- /STUB linker option
- Windows API [C++], attaching MS-DOS stub program
- -STUB linker option
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2bb7d1b9f56e7cea5d476d5ece6bdfab50fbe7a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="stub-ms-dos-stub-file-name"></a>/STUB (MS-DOS スタブ ファイル名)
```  
/STUB:filename  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *ファイル名*  
 MS-DOS アプリケーションです。  
  
## <a name="remarks"></a>コメント  
 /STUB オプションは、MS-DOS スタブ プログラムを Win32 プログラムにアタッチします。  
  
 MS-DOS でファイルが実行された場合は、スタブ プログラムが呼び出されます。 適切なメッセージです。 通常が表示されます。ただし、有効な任意 MS-DOS アプリケーションでは、スタブ プログラムを指定できます。  
  
 指定、 *filename*のコマンドラインでは、コロン (:) の後にスタブ プログラムです。 リンカー チェック*filename*し、ファイルが、実行可能ファイルではない場合、エラー メッセージを発行します。 プログラムは、.exe ファイルである必要があります。スタブ プログラム .com ファイルが正しくありません。  
  
 このオプションを使用しない場合、リンカーには、次のメッセージを発行する既定のスタブ プログラムがアタッチされます。  
  
```  
This program cannot be run in MS-DOS mode.  
```  
  
 仮想デバイス ドライバーを作成するときに*filename* (WINNT で定義されている IMAGE_DOS_HEADER 構造体を含むファイル名を指定することができます。H) をクリックし、既定のヘッダーではなく、VXD で使用します。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  オプションを入力、**追加オプション**ボックス。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)