---
title: "Choosing a Transparent or Opaque Background (Image Editor for Icons) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opaque backgrounds"
  - "background colors, images"
  - "colors [C++], image"
  - "Image editor [C++], transparent or opague backgrounds"
  - "background images"
  - "images [C++], transparency"
  - "images [C++], opaque background"
  - "transparent backgrounds"
  - "transparency, background"
  - "transparent backgrounds, images"
ms.assetid: 61b743d9-c86b-405d-9a81-0806431b4363
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Choosing a Transparent or Opaque Background (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イメージから選択領域を移動またはコピーする場合、現在の背景色と一致する選択領域内のピクセルは既定では透明で、移動先またはコピー先のピクセルを隠すことはありません。  
  
 透明な背景 \(既定値\) と不透明な背景の間で切り替えができます。  選択ツールを使用している場合は、以下の図に示すように \[イメージ エディター\] ツール バーのオプション セレクターに \[透明な背景\] オプションと \[不透明な背景\] オプションが表示されます。  
  
 ![背景のオプション &#45; 非透過または透過](../windows/media/vcimageeditoropaqtranspback.gif "vcImageEditorOpaqTranspBack")  
\[イメージ エディター\] ツール バーの \[透明な背景\] オプションと \[不透明な背景\] オプション  
  
### 透明な背景と不透明な背景を切り替えるには  
  
1.  \[イメージ エディター\] ツール バーの \[オプション\] セレクターをクリックし、適切な背景をクリックします。  
  
    -   \[不透明な背景\] : 既存のイメージは、選択領域全体で隠されます。  
  
    -   \[透明な背景\] : 既存のイメージは、選択領域のうち現在の背景色と一致する色で表示されます。  
  
 または  
  
-   \[イメージ\] メニューの \[背景色を不透明にする\] を選択または選択解除します。  
  
 選択領域が既に有効になっている間に背景色を変更し、イメージの透明な部分を変更できます。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 要件  
  
 なし  
  
## 参照  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Working with Color](../mfc/working-with-color-image-editor-for-icons.md)