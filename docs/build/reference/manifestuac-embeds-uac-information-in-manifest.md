---
title: "-MANIFESTUAC (マニフェストに UAC 情報) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.UACUIAccess
- VC.Project.VCLinkerTool.UACExecutionLevel
- VC.Project.VCLinkerTool.EnableUAC
dev_langs: C++
helpviewer_keywords:
- /MANIFESTUAC linker option
- MANIFESTUAC linker option
- -MANIFESTUAC linker option
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 979c93226adc49677581a22e2357ad7a65c581b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="manifestuac-embeds-uac-information-in-manifest"></a>/MANIFESTUAC (UAC 情報をマニフェストに組み込む)
ユーザー アカウント制御 (UAC) 情報をプログラム マニフェストに組み込むかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/MANIFESTUAC  
/MANIFESTUAC:NO  
/MANIFESTUAC:fragment  
/MANIFESTUAC:level=_level  
/MANIFESTUAC:uiAccess=_uiAccess  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fragment`  
 `level` 値および `uiAccess` 値を格納する文字列。 詳細については、このトピックで後述する「解説」を参照してください。  
  
 `_level`  
 いずれかの*asInvoker*、 *highestAvailable*、または*requireAdministrator*です。 既定値は asInvoker です。 詳細については、このトピックで後述する「解説」を参照してください。  
  
 `_uiAccess`  
 アプリケーションがユーザー インターフェイスの保護レベルをバイパスし、入力をデスクトップ上のアクセス許可の高いウィンドウにアクセスできるようにするには `true`、それ以外の場合は `false`。 既定値は `false` です。 `true` の設定は、ユーザー インターフェイスのユーザー補助アプリケーションでのみ行います。  
  
## <a name="remarks"></a>コメント  
 コマンド ラインで複数の /MANIFESTUAC オプションを指定した場合は、最後に入力したオプションが優先されます。  
  
 /MANIFESTUAC:level に指定できるのは、次のとおりです。  
  
-   `asInvoker`: アプリケーションは、アプリケーションを開始したプロセスと同じアクセス許可で実行されます。 アプリケーションを選択して上位の権限レベルに昇格させる**管理者として実行**です。  
  
-   highestAvailable: アプリケーションは、可能な限り高いアクセス許可レベルで実行されます。 アプリケーションを開始するユーザーが管理者グループのメンバーである場合、このオプションは requireAdministrator と同じです。 使用可能な最も高いアクセス許可レベルが、開始したプロセスのレベルより高い場合は、資格情報の入力が求められます。  
  
-   requireAdministrator: アプリケーションは管理者のアクセス許可で実行されます。 アプリケーションを開始するユーザーは、管理者グループのメンバーである必要があります。 開始したプロセスが管理者のアクセス許可で実行されない場合は、資格情報の入力が求められます。  
  
 /MANIFESTUAC:fragment オプションを使用することにより、level 値と uiAccess 値の指定を 1 ステップで行うことができます。 fragment は、次の形式で指定します。  
  
```  
"level=[ asInvoker | highestAvailable | requireAdministrator ] uiAccess=[ true | false ]"  
```  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**マニフェスト ファイル**プロパティ ページ。  
  
5.  変更、**を有効にするユーザー アカウント制御 (UAC)**、 **UAC の実行レベル**、および**UAC による UI 保護のバイパス**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A>、<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A>、および <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A> を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)