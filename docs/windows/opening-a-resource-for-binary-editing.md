---
title: "Opening a Resource for Binary Editing | Microsoft Docs"
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
  - "vc.editors.binary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binary data, editing"
  - "resources [Visual Studio], opening for binary editing"
ms.assetid: d3cdb0e4-da66-410d-8e49-b29073ff2929
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Opening a Resource for Binary Editing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### バイナリ編集用に Windows デスクトップ リソースを開くには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)で、編集の対象となる特定のリソース ファイルを選択します。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  リソースを右クリックし、ショートカット メニューから **\[バイナリー データを開く\]** をクリックします。  
  
    > [!NOTE]
    >  [リソース ビュー](../windows/resource-view-window.md) ウィンドウを使用して Visual Studio で認識されない書式のリソースを開く場合 \(RCDATA やカスタム リソースなど\)、リソースは自動的にバイナリ エディターで開かれます。  
  
### バイナリ編集の対象となるマネージ リソースを開くには  
  
1.  ソリューション エクスプローラーで、編集の対象となる特定のリソース ファイルを選択します。  
  
2.  リソースを右クリックして、ショートカット メニューから **\[プログラムから開く\]** を選択します。  
  
3.  **\[プログラムから開く\]** ダイアログ ボックスで、**バイナリ エディター**を選択します。  
  
    > [!NOTE]
    >  [イメージ エディター](../mfc/image-editor-for-icons.md)と[バイナリ エディター](../mfc/binary-editor.md)を使用して、マネージ プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージ リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。  
  
    > [!NOTE]
    >  マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
 ![バイナリ エディター](../Image/vcBinaryEditor2.gif "vcBinaryEditor2")  
バイナリ エディターに表示されるダイアログ ボックスのバイナリ データ  
  
 バイナリ エディターでは、特定の ASCII 値のみが表されます \(0x20 ～ 0x7E\)。 拡張文字は、バイナリ エディターの ASCII 値セクション \(右側のパネル\) にピリオドで表示されます。 "印刷可能" な文字は、ASCII 値の 32 ～ 126 です。  
  
> [!NOTE]
>  別のエディター ウィンドウで既に編集中のリソースに対してバイナリ エディターを使用する場合、他のエディター ウィンドウをまず閉じてください。  
  
 **必要条件**  
  
 なし  
  
## 参照  
 [Binary Editor](../mfc/binary-editor.md)