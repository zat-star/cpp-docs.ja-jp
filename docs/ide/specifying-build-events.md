---
title: "ビルド イベントの指定 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.IVCEventTool.CommandLine"
  - "VC.Project.IVCEventTool.ExcludedFromBuild"
  - "VC.Project.IVCEventTool.Description"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ビルド イベント [C++]"
  - "ビルド イベント [C++], 指定"
  - "ビルド [C++], カスタマイズ (C++ を)"
  - "ビルド [C++], イベント"
  - "カスタム ビルド ステップ [C++], ビルド イベント"
  - "イベント [C++], ビルド"
  - "ビルド後のイベント"
  - "Pre-Link イベント"
ms.assetid: 788a6c18-2dbe-4a49-8cd6-86c1ad7a95cc
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# ビルド イベントの指定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ビルド イベントを使用して、ビルドを開始する前、リンク プロセスの前、またはビルドの終了後に実行するコマンドを指定できます。  
  
 ビルド イベントは、ビルド処理でこれらのポイントにビルドが正常に到達した場合にだけ実行されます。  ビルドでエラーが発生した場合、*ビルド後*のイベントは発生しません。リンク フェーズより前にエラーが発生した場合は、*リンク前*のイベントと*ビルド後*のイベントのどちらも発生しません。  また、ファイルをリンクする必要がない場合、*リンク前*のイベントは発生しません。  *リンク前*のイベントは、リンク ステップを含まないプロジェクトでは使用できません。  
  
 ビルドする必要のあるファイルがない場合、ビルド イベントは発生しません。  
  
 ビルド イベントの概要については、「[カスタム ビルド ステップとビルド イベントについて](../ide/understanding-custom-build-steps-and-build-events.md)」を参照してください。  
  
### ビルド イベントを指定するには  
  
1.  **ソリューション エクスプローラー**で、ビルド イベントを指定するプロジェクトを選択します。  
  
2.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)」を参照してください。  
  
3.  **\[ビルド イベント\]** フォルダーで、ビルド イベント プロパティ ページを選択します。  
  
4.  ビルド イベントに関連付けられているプロパティを指定します。  
  
    -   **\[コマンド ライン\]** に、コマンド プロンプトに指定する場合と同じようにコマンドを指定します。  有効なコマンドまたはバッチ ファイル、および必要な入力ファイルまたは出力ファイルを指定します。  バッチ ファイルの名前の先頭に **call** バッチ コマンドを指定して、すべての後続コマンドが実行されるようにする必要があります。  
  
         MSBuild マクロを使用して、複数の入力ファイルおよび出力ファイルをシンボルで指定できます。  ファイルの場所、またはファイル セットの名前を指定する方法[!INCLUDE[crabout](../Token/crabout_md.md)]「[ビルドのコマンドとプロパティのマクロ](../ide/common-macros-for-build-commands-and-properties.md)」を参照してください。  
  
         '%' 文字は MSBuild によって予約されているため、環境変数を指定する場合は、各 **%** エスケープ文字を 16 進数の **%25** エスケープ シーケンスに置き換えてください。  たとえば、**%WINDIR%** は **%25WINDIR%25** に置き換えます。  MSBuild は、環境変数にアクセスする前に、各 **%25** シーケンスを **%** 文字に置き換えます。  
  
    -   **\[説明\]** に、このイベントの説明を入力します。  この説明は、このイベントが発生したときに**出力**ウィンドウに出力されます。  
  
    -   イベントを実行しない場合は、**\[ビルドから除外\]** を **\[はい\]** に指定します。  
  
## 参照  
 [カスタム ビルド ステップとビルド イベントについて](../ide/understanding-custom-build-steps-and-build-events.md)   
 [ビルドのコマンドとプロパティのマクロ](../ide/common-macros-for-build-commands-and-properties.md)   
 [ビルドのカスタマイズのトラブルシューティング](../ide/troubleshooting-build-customizations.md)