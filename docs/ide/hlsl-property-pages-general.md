---
title: "[全般] ([HLSL] プロパティ ページ) | Microsoft Docs"
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
  - "VC.Project.FXCompilerTool.ShaderModel"
  - "VC.Project.FXCompilerTool.PreprocessorDefinitions"
  - "VC.Project.FXCompilerTool.ShaderType"
  - "VC.Project.FXCompilerTool.EnableDebuggingInformation"
  - "VC.Project.FXCompilerTool.AdditionalIncludeDirectories"
  - "VC.Project.FXCompilerTool.DisableOptimizations"
  - "VC.Project.FXCompilerTool.EntryPointName"
dev_langs: 
  - "C++"
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
caps.latest.revision: 8
caps.handback.revision: 8
author: "BrianPeek"
ms.author: "brpeek"
manager: "ghogen"
---
# [全般] ([HLSL] プロパティ ページ)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

HLSL コンパイラ \(fxc.exe\) の次のプロパティを設定するには、**\[全般\]** のプロパティ ページを使用します。  HLSL フォルダーの **\[全般\]** のプロパティ ページを表示する方法については、[方法 : \[プロパティ ページ\] でプロジェクトのプロパティを指定する](../Topic/How%20to:%20Specify%20Project%20Properties%20with%20Property%20Pages.md)を参照してください。  
  
## UIElement の一覧  
 **追加のインクルード ディレクトリ\]**  
 インクルード パスに一つ以上のディレクトリを追加します。  ディレクトリを区切るには、セミコロンを使用します。  
  
 このプロパティは **\/I\[path\]** のコマンド ライン引数に対応します。  
  
 **Entrypoint の名前**  
 シェーダーのエントリ ポイントを指定します。  既定では、値は **\[メイン\]** です。  
  
 このプロパティは **\/E\[name\]** のコマンド ライン引数に対応します。  
  
 **無効の最適化**  
 最適化を無効にする **\[はい \(\/Od\)\]** ; それ以外 **\[いいえ\]**。  既定では、値は **\[リリース\]** の構成の **\[デバッグ\]** 構成と **\[いいえ\]** の **\[はい \(\/Od\)\]** です。  
  
 HLSL のコンパイラへの **\/Od** のコマンド ライン引数が暗黙的に **\/Gfp** のコマンド ライン引数を追加しますが、出力 **\/Od** と **\/Gfp** のコマンド ライン引数の両方を明示的に渡すことによって生成される出力と同じ場合とされない場合があります。  
  
 **デバッグ情報を有効にします。**  
 デバッグ情報を有効にする **\[はい \(\/Zi\)\]** ; それ以外 **\[いいえ\]**。  既定では、値は **\[リリース\]** の構成の **\[デバッグ\]** 構成と **\[いいえ\]** の **\[はい \(\/Zi\)\]** です。  
  
 **\[シェーダーの種類\]**  
 シェーダーの種類を指定します。  異なる種類の図のパイプラインのシェーダーの実装の異なる部分。  特定の種類のシェーダーはシェーダー モデル 5.で—例、計算のシェーダーの \(… **\[シェーダー モデル\]** のプロパティで指定\) でのみ使用できる最新のシェーダー モデル導入されました。  
  
 このプロパティは HLSL コンパイラに **\/T \[type\]\_\[model\]** のコマンド ライン引数の **\[type\]** の部分に対応します。  **\[Shader Models\]** のプロパティは、引数の **\[model\]** の部分を指定します。  
  
 **\[シェーダー モデル\]**  
 シェーダー モデルを指定します。  異なるシェーダー モデルによって異なる機能があります。  一般に、最新のシェーダー モデルを拡張された機能を提供しますが、最新のグラフィックス ハードウェアをシェーダー コードを実行するように要求されます。  \(**\[シェーダーの種類\]** のプロパティで指定\)、特定の種類のシェーダー シェーダー モデル 5.の例では、計算のシェーダー モデルの最新のシェーダーでのみ使用できる導入されました。  
  
 このプロパティは HLSL コンパイラに **\/T \[type\]\_\[model\]** のコマンド ライン引数の **\[model\]** の部分に対応します。  **\[シェーダーの種類\]** のプロパティは、引数の **\[type\]** の部分を指定します。  
  
 **\[プリプロセッサの定義\]**  
 一つ以上のプリプロセッサ シンボルの定義を HLSL のソース・コード ファイルに適用するようにします。  シンボルの定義を区切るには、セミコロンを使用します。  
  
 このプロパティは HLSL コンパイラに **\/D \[definitions\]** のコマンド ライン引数に対応します。  
  
## 参照  
 [\[HLSL\] プロパティ ページ](../Topic/HLSL%20Property%20Pages.md)   
 [\[詳細\] \(\[HLSL\] プロパティ ページ\)](../Topic/HLSL%20Property%20Pages:%20Advanced.md)   
 [\[HLSL\] プロパティ ページ: 出力ファイル](../Topic/HLSL%20Property%20Pages:%20Output%20Files.md)