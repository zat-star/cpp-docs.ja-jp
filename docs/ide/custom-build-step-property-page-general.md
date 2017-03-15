---
title: "[カスタム ビルド ステップ] プロパティ ページ: 全般 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCustomBuildStep.AdditionalInputs"
  - "VC.Project.VCCustomBuildStep.CustomBuildAfterTargets"
  - "VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets"
  - "VC.Project.VCCustomBuildStep.Outputs"
  - "VC.Project.VCCustomBuildStep.Message"
  - "VC.Project.VCCustomBuildStep.Command"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "プロジェクトのプロパティ、カスタム ビルド ステップ"
  - "カスタム ビルド ステップ (汎用)"
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# [カスタム ビルド ステップ] プロパティ ページ: 全般
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロジェクトにおけるプロジェクト構成とターゲット プラットフォームの組み合わせごとに、プロジェクトをビルドするときに実行するカスタム ステップを指定できます。  
  
## UIElement の一覧  
 **\[コマンド ライン\]**  
 カスタム ビルド ステップによって実行されるコマンド。  
  
 **\[説明\]**  
 カスタム ビルド ステップを実行するときに表示されるメッセージ。  
  
 **\[出力\]**  
 カスタム ビルド ステップが生成する出力ファイル。  この設定は、インクリメンタル ビルドが正しく機能するために必要です。  
  
 **\[追加の依存ファイル\]**  
 カスタム ビルド ステップで使用する追加の入力ファイルの、セミコロンで区切られた一覧。  
  
 **\[以後に実行\] および \[以前に実行\]**  
 ビルド プロセスでカスタム ビルド ステップが実行されるタイミングを、表示されているターゲットを基準にして定義します。  最もよく表示されるターゲットは BuildGenerateSources、BuildCompile、および BuildLink です。これらはビルド プロセスの主なステップを表しています。  また、Midl、CLCompile、および Link もよく表示されるターゲットです。  
  
 \[出力をコンテンツとして扱う\]  
 このオプションは、.appx パッケージにすべてのコンテンツ ファイルが含まれる Windows ストアまたは Windows Phone アプリに対してのみ意味を持ちます。  
  
### カスタム ビルド ステップを指定するには  
  
1.  メニュー バーで **\[プロジェクト\]**、**\[プロパティ\]** の順に選択します。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[プロパティ ページ\]** ダイアログ ボックスで、**\[構成プロパティ\]**、**\[カスタム ビルド ステップ\]**、**\[全般\]** ページの順に移動します。  
  
3.  設定を変更します。  
  
## 参照  
 [プロパティ ページ](../ide/property-pages-visual-cpp.md)