---
title: "Creating a Device Image (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.icon"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cursors [C++], creating"
  - "icons [C++], creating"
  - "display devices"
  - "display devices, creating image"
  - "images [C++], creating for display devices"
  - "icons [C++], inserting"
ms.assetid: 5a536928-32df-4ace-beb1-1521ce3b871f
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Creating a Device Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アイコン リソースまたはカーソル リソースを新規作成するときに、イメージ エディターではイメージが最初に特定のスタイルで作成されます。アイコンの場合は 32 × 32 の 16 色、カーソルの場合は 32 × 32 のモノクロです。  初期のアイコンやカーソルにサイズとスタイルの異なるイメージを追加し、追加したイメージを必要に応じてさまざまなディスプレイ デバイスに合わせて編集できます。  また、既存のイメージ種類から切り取りと貼り付けの操作によって、またはグラフィック プログラムで作成したビットマップからも、イメージを編集できます。  Windows で使用されるアイコン サイズの詳細については、Windows SDK 資料の「[アイコン](_win32_Icons_cpp)」を参照してください。  
  
 [イメージ エディター](../mfc/image-editor-for-icons.md)でアイコン リソースやカーソル リソースを開くと、既定では現在のディスプレイ デバイスに最も近いイメージが開きます。  
  
### アイコンまたはカーソルを新規作成するには  
  
1.  [&#91;リソース ビュー&#93;](../windows/resource-view-window.md) で、.rc ファイルを右クリックし、ショートカット メニューの **\[リソースの挿入\]** を選択します   \(カーソルなどの既存のイメージ リソースがすでに .rc ファイルにある場合は、単純に **\[Cursor\]** フォルダーを右クリックして、ショートカット メニューの **\[Cursor を挿入\]** を選択します\)。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  [&#91;リソースの挿入&#93; ダイアログ ボックス](../Topic/Add%20Resource%20Dialog%20Box.md)で、**\[Icon\]** または **\[Cursor\]** を選択し、**\[新規作成\]** をクリックします。  アイコンの場合は、32 × 32 の 16 色のアイコンを持つアイコン リソースが作成されます。  カーソルの場合は、32 × 32 のモノクロ \(2 色\) のイメージが作成されます。  
  
     **\[リソースの挿入\]** ダイアログ ボックスで、イメージ リソースの種類の横に正符号 \(**\+**\) が表示される場合は、ツール バーのテンプレートが使用可能であることを示します。  正符号をクリックしてテンプレートの一覧を展開します。次に、テンプレートを選択し、\[新規作成\] をクリックします。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 **要件**  
  
 なし  
  
## 参照  
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Icons and Cursors: Image Resources for Display Devices](../mfc/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)