---
title: "/STUB (MS-DOS スタブ ファイル名) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/stub"
  - "VC.Project.VCLinkerTool.DosStub"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/STUB リンカー オプション"
  - "MS-DOS スタブ ファイル名リンカー オプション"
  - "STUB リンカー オプション"
  - "-STUB リンカー オプション"
  - "Win32 [C++], アタッチ (MS-DOS スタブ プログラム)"
  - "Windows API [C++], アタッチ (MS-DOS スタブ プログラム)"
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /STUB (MS-DOS スタブ ファイル名)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/STUB:filename  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 *filename*  
 MS\-DOS アプリケーション。  
  
## 解説  
 \/STUB オプションは、MS\-DOS スタブ プログラムを Win32 プログラムにアタッチします。  
  
 スタブ プログラムとは、ファイルを MS\-DOS で実行したときに起動するプログラムです。  スタブ プログラムは通常、メッセージを表示するだけのものです。ただし、有効な MS\-DOS のアプリケーションの場合、どのアプリケーションでもスタブ プログラムとして使用できます。  
  
 コマンド ラインで、スタブ プログラムとして設定するファイル名をコロン \(:\) の後ろに指定します。  リンカーによって *filename* がチェックされ、実行可能ファイルでない場合はエラー メッセージが表示されます。  スタブ プログラムとして設定できるのは、.exe ファイルだけです。.com ファイルはスタブ プログラムとして設定できません。  
  
 このオプションが指定されていないと、次のメッセージを出力する既定のスタブ プログラムがアタッチされます。  
  
```  
This program cannot be run in MS-DOS mode.  
```  
  
 仮想デバイス ドライバーをビルドする場合は、既定のヘッダーではなく VxD で使用される IMAGE\_DOS\_HEADER 構造体 \(WINNT.H で定義されている\) を含むファイル名を *filename* に指定できます。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにオプションを入力します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)