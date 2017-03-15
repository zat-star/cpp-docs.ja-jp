---
title: "/MANIFESTUAC (UAC 情報をマニフェストに組み込む) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.UACUIAccess"
  - "VC.Project.VCLinkerTool.UACExecutionLevel"
  - "VC.Project.VCLinkerTool.EnableUAC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFESTUAC リンカー オプション"
  - "MANIFESTUAC リンカー オプション"
  - "-MANIFESTUAC リンカー オプション"
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /MANIFESTUAC (UAC 情報をマニフェストに組み込む)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ユーザー アカウント制御 \(UAC\) 情報をプログラム マニフェストに組み込むかどうかを指定します。  
  
## 構文  
  
```  
/MANIFESTUAC  
/MANIFESTUAC:NO  
/MANIFESTUAC:fragment  
/MANIFESTUAC:level=_level  
/MANIFESTUAC:uiAccess=_uiAccess  
```  
  
#### パラメーター  
 `fragment`  
 `level` 値および `uiAccess` 値を格納する文字列。  詳細については、このトピックで後述する「解説」を参照してください。  
  
 `_level`  
 *asInvoker*、*highestAvailable*、*requireAdministrator* のいずれか。  既定値は asInvoker です。  詳細については、このトピックで後述する「解説」を参照してください。  
  
 `_uiAccess`  
 アプリケーションがユーザー インターフェイスの保護レベルをバイパスし、入力をデスクトップ上のアクセス許可の高いウィンドウにアクセスできるようにするには `true`、それ以外の場合は `false`。  既定値は `false` です。  `true` の設定は、ユーザー インターフェイスのユーザー補助アプリケーションでのみ行います。  
  
## 解説  
 コマンド ラインで複数の \/MANIFESTUAC オプションを指定した場合は、最後に入力したオプションが優先されます。  
  
 \/MANIFESTUAC:level に指定できるのは、次のとおりです。  
  
-   `asInvoker`: アプリケーションは、アプリケーションを開始したプロセスと同じアクセス許可で実行されます。  **\[管理者として実行\]** を選択すると、アプリケーションをより高いアクセス許可に昇格させることができます。  
  
-   highestAvailable: アプリケーションは、可能な限り高いアクセス許可レベルで実行されます。  アプリケーションを開始するユーザーが管理者グループのメンバーである場合、このオプションは requireAdministrator と同じです。  使用可能な最も高いアクセス許可レベルが、開始したプロセスのレベルより高い場合は、資格情報の入力が求められます。  
  
-   requireAdministrator: アプリケーションは管理者のアクセス許可で実行されます。  アプリケーションを開始するユーザーは、管理者グループのメンバーである必要があります。  開始したプロセスが管理者のアクセス許可で実行されない場合は、資格情報の入力が求められます。  
  
 \/MANIFESTUAC:fragment オプションを使用することにより、level 値と uiAccess 値の指定を 1 ステップで行うことができます。  fragment は、次の形式で指定します。  
  
```  
"level=[ asInvoker | highestAvailable | requireAdministrator ] uiAccess=[ true | false ]"  
```  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[リンカー\]** ノードを展開します。  
  
4.  **\[マニフェスト ファイル\]** プロパティ ページをクリックします。  
  
5.  **\[ユーザー アカウント制御 \(UAC\) を有効にする\]**、**\[UAC の実行レベル\]**、および **\[UAC による UI 保護のバイパス\]** の各プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A>、<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A>、および <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A> を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)