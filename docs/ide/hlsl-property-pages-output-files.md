---
title: "[HLSL] プロパティ ページ: 出力ファイル | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.FXCompilerTool.AssemblerOutput"
  - "VC.Project.FXCompilerTool.ObjectFileOutput"
  - "VC.Project.FXCompilerTool.HeaderFileOutput"
  - "VC.Project.FXCompilerTool.VariableName"
  - "VC.Project.FXCompilerTool.AssemblerOutputFile"
dev_langs: 
  - "C++"
ms.assetid: c5ba1e72-30de-43eb-a15a-5b0ae58e55c2
caps.latest.revision: 5
caps.handback.revision: 5
author: "BrianPeek"
ms.author: "brpeek"
manager: "ghogen"
---
# [HLSL] プロパティ ページ: 出力ファイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

HLSL コンパイラ \(fxc.exe\) の次のプロパティを設定するには、**\[出力ファイル\]** のプロパティを使用します。  HLSL フォルダーの **\[出力ファイル\]** のプロパティ ページを表示する方法については、[方法 : \[プロパティ ページ\] でプロジェクトのプロパティを指定する](../Topic/How%20to:%20Specify%20Project%20Properties%20with%20Property%20Pages.md)を参照してください。  
  
## UIElement の一覧  
 **\[ヘッダー変数名\]**  
 使用されるエンコードされた HLSL のオブジェクト コードである配列の名前を指定します。  配列は HLSL コンパイラによって出力されるヘッダー ファイルに入っています。  ヘッダー ファイル名は、**\[ヘッダー ファイル名\]** のプロパティで指定します。  
  
 このプロパティは **\/Vn\[name\]** のコマンド ライン引数に対応します。  
  
 **\[ヘッダー ファイル名\]**  
 HLSL コンパイラによって出力されるヘッダー ファイルの名前を指定します。  ヘッダーは配列にエンコードされたオブジェクト HLSL のコードが含まれています。  配列の名前は **\[ヘッダー変数名\]** のプロパティで指定します。  
  
 このプロパティは **\/Fh\[name\]** のコマンド ライン引数に対応します。  
  
 **オブジェクトのファイル名**  
 HLSL コンパイラによって出力されるオブジェクト ファイルの名前を指定します。  既定では、値は **\[$\(OutDir\)%\(Filename\).cso\]** です。  
  
 このプロパティは **\/Fo\[name\]** のコマンド ライン引数に対応します。  
  
 **アセンブラーの出力**  
 アセンブリ言語のステートメントだけを出力する**アセンブリのみが一覧 \(\/Fc\)**  16 進数の両方のアセンブリ言語ステートメント、対応する操作コードを出力する**アセンブリ コード、および 16 進数 \(\/Fx\)** 。  既定では、リストは出力されません。  
  
 **アセンブラーの出力ファイル**  
 HLSL コンパイラによって出力されるアセンブリ一覧のファイルの名前を指定します。  
  
 このプロパティは **\/Fc\[name\]** と **\/Fx \[name\]** のコマンド ライン引数に対応します。  
  
## 参照  
 [\[HLSL\] プロパティ ページ](../Topic/HLSL%20Property%20Pages.md)   
 [\[全般\] \(\[HLSL\] プロパティ ページ\)](../Topic/HLSL%20Property%20Pages:%20General.md)   
 [\[詳細\] \(\[HLSL\] プロパティ ページ\)](../Topic/HLSL%20Property%20Pages:%20Advanced.md)