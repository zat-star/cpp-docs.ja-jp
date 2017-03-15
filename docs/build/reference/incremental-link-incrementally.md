---
title: "/INCREMENTAL (インクリメンタル リンクを行う) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/incremental"
  - "VC.Project.VCLinkerTool.LinkIncremental"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/INCREMENTAL リンカー オプション"
  - "INCREMENTAL リンカー オプション"
  - "-INCREMENTAL リンカー オプション"
  - "インクリメンタル リンク"
  - "リンク オプション (インクリメンタル)"
  - "LINK ツール [C++], オプション (フル リンクの)"
ms.assetid: 135656ff-94fa-4ad4-a613-22e1a2a5d16b
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /INCREMENTAL (インクリメンタル リンクを行う)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/INCREMENTAL[:NO]  
```  
  
## 解説  
 リンカーによる、インクリメンタル リンクの処理方法を制御します。  
  
 既定では、インクリメンタル リンクは実行されます。  既定で設定されたインクリメンタル リンクを無効にするには、\/INCREMENTAL:NO と指定します。  
  
 インクリメンタル リンクされたプログラムは、フル リンクされたプログラムと機能的には等価です。  しかし、これは以降のインクリメンタル リンク用に用意されているものであるため、インクリメンタル リンクされた実行可能 \(.exe\) ファイルとダイナミック リンク ライブラリ \(DLL: Dynamic\-Link Library\) には次の特徴があります。  
  
-   コードとデータが埋め込まれているため、フル リンクされたプログラムよりサイズが大きくなります。埋め込みを行うと、リンカーは、.exe ファイルを再作成することなく、機能やデータのサイズを拡張できます。  
  
-   ジャンプ サンクを使って、新しいアドレスに関数を再配置する場合があります。  
  
    > [!NOTE]
    >  最終リリース ビルドに埋め込みやサンクが含まれないようにするには、プログラムをフル リンクします。  
  
 既定の設定に関係なくインクリメンタル リンクを行うには、\/INCREMENTAL と指定します。  このオプションが指定されているにもかかわらず、インクリメンタル リンクを実行できない場合、リンカーは警告メッセージを表示して、プログラムのフル リンクを行います。  一部のオプションや状況によっては、\/INCREMENTAL が無効になる場合もあります。  
  
 大半のプログラムでは、インクリメンタル リンクができます。  ただし、変更箇所が大きすぎたり、インクリメンタル リンクと矛盾するオプションが指定されていると、実行できません。  フル リンクを実行するには、次のいずれかを行います。  
  
-   インクリメンタル リンクをオフ \(\/INCREMENTAL:NO\) にする。  
  
-   \/OPT:REF オプションを指定する。  
  
-   \/OPT:ICF オプションを指定する。  
  
-   \/OPT:LBR オプションを指定する。  
  
-   \/ORDER オプションを指定する。  
  
 [\/DEBUG](../../build/reference/debug-generate-debug-info.md) を指定すると \/INCREMENTAL も指定されます。  
  
 以下の場合もフル リンクが行われます。  
  
-   インクリメンタル ステータス \(.ilk\) ファイルが見つからない場合。LINK では、以降のインクリメンタル リンク用に新しい .ilk ファイルを作成します。  
  
-   .ilk ファイルに対する書き込み権限がない場合。LINK では .ilk ファイルを無視して、フル リンクを行います。  
  
-   出力ファイル .exe または .dll が見つからない場合。  
  
-   .ilk、.exe、または .dll のタイムスタンプを変更した場合。  
  
-   LINK オプションを変更した場合。  ビルド間で LINK オプションを変更すると、ほとんどの場合、フル リンクが行われます。  
  
-   オブジェクト \(.obj\) ファイルを追加または省略した場合。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーを選択します。  
  
3.  **\[全般\]** プロパティ ページをクリックします。  
  
4.  **"インクリメンタル リンクを有効にする"** プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkIncremental%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)