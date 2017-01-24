---
title: "Previewing Resources | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.resvw.resource.previewing"
  - "vs.resvw.resource.previewing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], viewing"
  - "resource previews"
  - "code, viewing"
ms.assetid: d6abda66-0e2b-4ac3-a59a-a57b8c6fb70b
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Previewing Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リソースをプレビューすると、グラフィカル リソースを開かずに表示できます。  リソース識別子は数字に変換されるため、コンパイル後の実行可能ファイルでもプレビューが役立ちます。  数字の識別子から得られる情報は十分ではないため、リソースをプレビューしてリソースをすばやく識別できます。  
  
 次に示すリソースの種類のレイアウトをプレビューできます。  
  
-   ビットマップ  
  
-   ダイアログ  
  
-   Icon  
  
-   メニュー  
  
-   Cursor  
  
-   ツール バー  
  
 アクセラレータ、マニフェスト、ストリング テーブル、バージョン情報の各リソースには、視覚的なプレビュー機能は適用されません。  
  
### リソースをプレビューするには  
  
1.  [&#91;リソース ビュー&#93;](../windows/resource-view-window.md) またはドキュメント ウィンドウで、IDD\_ABOUTBOX などの目的のリソースを選択します。  
  
     **メモ** プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)で、\[プロパティ ページ\] をクリックします。  
  
     または  
  
3.  **\[表示\]** メニューの **\[プロパティ ページ\]** をクリックします。  
  
     リソースのプロパティ ページが開き、リソースのプレビューが表示されます。  上下の方向キーを使用して、\[リソース ビュー\] またはドキュメント ウィンドウのツリー コントロールを移動できます。  \[プロパティ ページ\] は開いたままになり、フォーカスがあるプレビュー可能なリソースが表示されます。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 **要件**  
  
 Win32  
  
## 参照  
 [How to: Open a Resource Script File Outside of a Project \(Standalone\)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Resource Editors](../mfc/resource-editors.md)