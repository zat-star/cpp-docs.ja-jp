---
title: "Viewing and Editing Resources in a Resource Editor | Microsoft Docs"
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
  - "vs.resourceview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], viewing"
  - "rc files, viewing resources"
  - "Resource View pane"
  - "layouts, previewing resource"
  - "code, viewing resources"
  - "resource editors, viewing resources"
  - ".rc files, viewing resources"
  - "resources [Visual Studio], editing"
ms.assetid: ba8bdc07-3f60-43c7-aa5c-d5dd11f0966e
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Viewing and Editing Resources in a Resource Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リソースの種類ごとに固有のリソース エディターがあります。  関連付けられたエディターを使用して、リソースの再整列、サイズ変更、コントロールと機能の追加を行ったり、リソースの外観を変更したりできます。  リソースを[テキスト形式](../windows/how-to-open-a-resource-script-file-in-text-format.md)および[バイナリ形式](../mfc/opening-a-resource-for-binary-editing.md)で編集することもできます。  
  
 リソースの種類には、ビットマップ、アイコン、カーソル、ツール バー、および html の各ファイルのように、それ自体をさまざまな方法でインポートおよび使用できる個別のファイルもあります。  これらのリソースには、[リソース識別子](../mfc/symbols-resource-identifiers.md)だけでなくファイル名があります。  Win32 プロジェクトのダイアログ、メニュー、ストリング テーブルなどのその他のリソースは、リソース スクリプト \(.rc\) ファイルまたはリソース テンプレート \(.rct\) ファイルの一部にだけ存在しています。  
  
> [!NOTE]
>  リソースのプロパティは[プロパティ ウィンドウを使用して変更できます](../windows/changing-the-properties-of-a-resource.md)。  
  
## Win32 リソース  
 [リソース ビュー](../windows/resource-view-window.md) ペインで Win32 リソースにアクセスできます。  
  
#### リソース エディターで Win32 リソースを表示するには  
  
1.  \[表示\] メニューの \[リソース ビュー\] をクリックします。  
  
2.  \[リソース ビュー\] ウィンドウが最前面に表示されていないときは、\[リソース ビュー\] タブをクリックして手前に表示します。  
  
3.  \[リソース ビュー\] で、表示するリソースを含むプロジェクトのフォルダーを展開します。  たとえば、ダイアログのリソースを表示する場合は、\[Dialog\] フォルダーを展開します。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
4.  IDD\_ABOUTBOX などのリソースをダブルクリックします。  
  
     リソースが適切なエディターで開きます。  たとえば、ダイアログ リソースの場合は、リソースがダイアログ エディターで開きます。  
  
     [プロジェクトを開かずに .rc \(リソース スクリプト\) ファイルのリソースを表示する](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)こともできます。  
  
#### 既存の Win 32 リソースを削除するには  
  
1.  \[リソース ビュー\] で、リソースの種類についてのノードを展開します。  
  
2.  削除するリソースを右クリックし、ショートカット メニューの \[削除\] をクリックします。  
  
    > [!NOTE]
    >  プロジェクト外部のドキュメント ウィンドウで .rc ファイルを開いている場合は、ショートカット メニューの同じコマンドを使用してリソースを削除できます。  
  
## マネージ プロジェクトのリソース  
 マネージ プロジェクトではリソース スクリプト ファイルを使用しないため、リソースは**ソリューション エクスプローラー**から開く必要があります。  [イメージ エディター](../mfc/image-editor-for-icons.md)と[バイナリ エディター](../mfc/binary-editor.md)を使用して、マネージ プロジェクトのリソース ファイルを操作できます。  編集の対象となるマネージ リソースは、リンク リソースである必要があります。  Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
#### リソース エディターでマネージ リソースを表示するには  
  
1.  ソリューション エクスプローラーで、Bitmap1.bmp などのリソースをダブルクリックします。  
  
     リソースが適切なエディターで開きます。  
  
#### 既存のマネージ リソースを削除するには  
  
1.  ソリューション エクスプローラーで、削除するリソースの文字列を右クリックし、ショートカット メニューの \[削除\] をクリックします。  
  
### 要件  
 なし  
  
## 参照  
 [Resource Editors](../mfc/resource-editors.md)