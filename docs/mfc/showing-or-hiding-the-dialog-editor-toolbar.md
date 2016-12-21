---
title: "[ダイアログ エディター] ツール バーの表示と非表示 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コントロール [C++]、ダイアログ エディター ツール バーを表示または非表示"
  - "ツール バー [C++]、表示"
  - "ツール バー [C++]、非表示"
  - "ダイアログ エディター、ツール バーの表示または非表示"
ms.assetid: 93c255e1-90eb-48b6-8602-450acda75bed
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# [ダイアログ エディター] ツール バーの表示と非表示
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ダイアログ エディターを開くと、ソリューションの最上部に \[ダイアログ エディター\] ツール バーが自動的に表示されます。  
  
### \[ダイアログ エディター\] ツール バー  
  
|Icon|説明|Icon|説明|  
|----------|--------|----------|--------|  
|![ダイアログのテスト ボタン](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|テスト ダイアログ|![左右均等配置ボタン](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|左右|  
|![左揃えボタン](../Image/vcDialogEditorAlignLefts.png "vcDialogEditorAlignLefts")|左揃え|![上下均等配置ボタン](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|下へ|  
|![右揃えボタン](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|右揃え|![幅を揃えるボタン](../Image/vcDialogEditorSameWidth.png "vcDialogEditorSameWidth")|幅を揃える|  
|![上揃えボタン](../Image/vcDialogEditorAlignTops.png "vcDialogEditorAlignTops")|上揃え|![高さを揃えるボタン](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|高さを揃える|  
|![下揃えボタン](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|下揃え|![同じサイズに揃えるボタン](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|同じサイズに揃える|  
|![垂直方向の中央揃えボタン](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|\[垂直方向\]|![グリッドの切り替えボタン](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|グリッドの切り替え|  
|![水平方向の中央揃えボタン](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|\[水平方向\]|![ガイドの切り替えボタン](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|ガイドの切り替え|  
  
 \[ダイアログ エディター\] ツール バーには、サイズや配置など、ダイアログ ボックスのコントロールのレイアウトを調整するためのボタンがあります。  \[ダイアログ エディター\] ツール バーのボタンは、\[書式\] メニューのコマンドに対応しています。  詳細については、「[ダイアログ エディターのアクセラレータ キー](../mfc/accelerator-keys-for-the-dialog-editor.md)」を参照してください。  
  
 ダイアログ エディターでは、使用可能なツール バーとウィンドウの一覧で、\[ダイアログ エディター\] ツール バーの表示と非表示を切り替えることができます。  
  
### \[ダイアログ エディター\] ツール バーの表示と非表示を切り替えるには  
  
1.  \[表示\] メニューの \[ツール バー\] をクリックし、サブメニューの \[ダイアログ エディター\] を選択します。  
  
    > [!NOTE]
    >  既定では、ダイアログ エディターでダイアログ ボックス リソースを開くと、\[ダイアログ エディター\] ツール バーが表示されます。ただし、このツール バーを明示的に閉じた場合は、次回にダイアログ ボックス リソースを開くときに起動する必要があります。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 要件  
  
 Win32  
  
## 参照  
 [Arrangement of Controls on Dialog Boxes](../mfc/arrangement-of-controls-on-dialog-boxes.md)   
 [How to: Create a Resource](../windows/how-to-create-a-resource.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Dialog Editor](../mfc/dialog-editor.md)