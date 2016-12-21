---
title: "Binary Editor | Microsoft Docs"
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
  - "vc.editors.binary.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "editors, Binary"
  - "resources [Visual Studio], editing"
  - "resource editors, Binary editor"
  - "Binary editor"
ms.assetid: 2483c48b-1252-4dbc-826b-82e6c1a0e9cb
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Binary Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!WARNING]
>  バイナリ エディターは Express Edition では使用できません。  
  
 バイナリ エディターを使うと、16 進形式または ASCII 形式を使用してバイナリ レベルでリソースを編集できます。 また、[&#91;検索&#93; コマンド](../Topic/Find%20Command.md)を使うと、ASCII 文字列や 16 進表現のバイト列を検索できます。 バイナリ エディターは、カスタム リソースや Visual Studio 環境でサポートされていない種類のリソースを表示したり、部分的に変更したりするときにだけ使うようにしてください。  
  
 バイナリ エディターを開くには、最初にメイン メニューの **\[ファイル &#124; 新規作成 &#124; ファイル\]** を選択し、編集するファイルを選択し、**\[開く\]** の横のドロップダウン矢印をクリックし、**\[ファイルを開くアプリケーションの選択 &#124; バイナリ エディター\]** をクリックします。  
  
> [!CAUTION]
>  ダイアログ ボックス、イメージ、メニューなどのリソースをバイナリ エディターで編集することは危険です。 編集方法が正しくないと、リソースを破損し、本来のエディターで読み取ることができなくなる場合があります。  
  
> [!TIP]
>  バイナリ エディターをさまざまな状況で使用している場合、マウスの右ボタンをクリックするとリソースに対応したショートカット メニューを表示できます。 使用できるコマンドは、ポインターの位置によって異なります。 たとえば、16 進の値が選ばれているバイナリ エディターをポイントした状態でクリックすると、ショートカット メニューには **\[切り取り\]**、**\[コピー\]**、**\[貼り付け\]** の各コマンドが表示されます。  
  
 バイナリ エディターでは、次の作業ができます。  
  
-   [バイナリ編集するリソースを開く](../mfc/opening-a-resource-for-binary-editing.md)  
  
-   [バイナリ データを編集する](../mfc/editing-binary-data.md)  
  
-   [バイナリ データを検索する](../mfc/finding-binary-data.md)  
  
-   [新しいカスタム リソースまたはデータ リソースを作成する](../mfc/creating-a-new-custom-or-data-resource.md)  
  
## マネージ リソース  
 [イメージ エディター](../mfc/image-editor-for-icons.md)とバイナリ エディターを使用して、マネージ プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージ リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
### 必要条件  
 なし  
  
## 参照  
 [Resource Editors](../mfc/resource-editors.md)