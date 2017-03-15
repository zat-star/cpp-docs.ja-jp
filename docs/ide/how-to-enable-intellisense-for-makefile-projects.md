---
title: "方法 : メイクファイル プロジェクトで IntelliSense を使用可能にする | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCNMakeTool.IntelliSense"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IntelliSense, メイクファイル プロジェクト"
  - "メイクファイル プロジェクト, IntelliSense"
ms.assetid: 9443f453-f18f-4f12-a9a1-ef9dbf8b188f
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# 方法 : メイクファイル プロジェクトで IntelliSense を使用可能にする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

特定のプロジェクト設定やコンパイラ オプションが正しく設定されていないと、IDE の Visual C\+\+ メイクファイル プロジェクトで IntelliSense を使用できません。  この手順を使用して、Visual Studio 開発環境でメイクファイル プロジェクトを開いているときに IntelliSense が動作するように、Visual C\+\+ メイクファイル プロジェクトを構成します。  
  
### IDE のメイクファイル プロジェクトで IntelliSense を使用可能にするには  
  
1.  **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[NMake\]** プロパティ ページを選択し、**\[IntelliSense\]** のプロパティを適切に変更します。  
  
    -   プリプロセッサ シンボルをメイクファイル プロジェクトに定義するように、**\[プリプロセッサの定義\]** プロパティを設定します。  詳細については、「[\/D \(プリプロセッサの定義\)](../build/reference/d-preprocessor-definitions.md)」を参照してください。  
  
    -   コンパイラがメイクファイル プロジェクトのプリプロセッサ ディレクティブに渡されるファイル参照を解決するために検索するディレクトリの一覧を指定するように **\[インクルードの検索パス\]** プロパティを設定します。  詳細については、「[\/I \(追加インクルード ディレクトリ\)](../build/reference/i-additional-include-directories.md)」を参照してください。  
  
         コマンド ウィンドウから CL.EXE を使用してビルドされるプロジェクトの場合は、メイクファイル プロジェクトのプリプロセッサ ディレクティブに渡されるファイル参照を解決するために、コンパイラはディレクトリを検索します。ここでは、このディレクトリが指定されるように、**INCLUDE** 環境変数を設定します。  
  
    -   メイクファイル プロジェクトのビルド時に処理されるヘッダー ファイルが指定されるように、**\[強制インクルード\]** プロパティを設定します。  詳細については、「[\/FI \(強制インクルード ファイルの名前の指定\)](../Topic/-FI%20\(Name%20Forced%20Include%20File\).md)」を参照してください。  
  
    -   プロジェクトの .NET アセンブリに渡される参照を解決するために、コンパイラはディレクトリを検索します。ここでは、このディレクトリの一覧が指定されるように、**\[アセンブリの検索パス\]** プロパティを設定します。  詳細については、「[\/AI \(メタデータ ディレクトリの指定\)](../build/reference/ai-specify-metadata-directories.md)」を参照してください。  
  
    -   メイクファイル プロジェクトのビルド時に使用される .NET アセンブリが指定されるように、**\[アセンブリの強制使用\]** プロパティを設定します。  詳細については、「[\/FU \(強制 \#using ファイルの名前の指定\)](../build/reference/fu-name-forced-hash-using-file.md)」を参照してください。  
  
    -   C\+\+ ファイルの解析時に追加のコンパイラ スイッチが Intellisense によって使用されることを指定するように **\[追加オプション\]** プロパティを設定します。  
  
4.  **\[OK\]** をクリックして、プロパティ ページを閉じます。  
  
5.  **\[すべてを保存\]** をクリックして、変更したプロジェクト設定を保存します。  
  
 Visual Studio 開発環境でメイクファイル プロジェクトを開き直し、**\[ソリューションのクリーン\]** を実行し、次にメイクファイル プロジェクトで **\[ソリューションのビルド\]** を実行します。  IntelliSense は IDE で正しく動作します。  
  
## 参照  
 [IntelliSense の使用方法](../Topic/Using%20IntelliSense.md)   
 [NMAKE リファレンス](../build/nmake-reference.md)   
 [方法 : 既存のコードから C\+\+ プロジェクトを作成する](../ide/how-to-create-a-cpp-project-from-existing-code.md)