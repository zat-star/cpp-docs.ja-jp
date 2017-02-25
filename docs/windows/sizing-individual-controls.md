---
title: "Sizing Individual Controls | Microsoft Docs"
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
  - "Size to Content command"
  - "size, controls"
  - "text, autosizing controls to fit text"
  - "controls [C++], sizing"
ms.assetid: 14ccba02-7171-463a-a121-7018cf1e2e5a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Sizing Individual Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

サイズ変更ハンドルを使用して、コントロールのサイズを変更します。  ポインターをサイズ変更ハンドルに置くと、ポインターの形が変化してコントロールをサイズ変更できる方向を示します。  アクティブなサイズ変更ハンドルは実線で表されます。サイズ変更ハンドルが中空の場合、コントロールのサイズはその軸に沿って変更できません。  
  
 また、コントロールのサイズを変更するには、コントロールをガイドやマージンに合わせて配置し、ガイドを移動する方法もあります。  
  
### コントロールのサイズを変更するには  
  
1.  コントロールを選択します。  
  
2.  サイズ変更ハンドルをドラッグしてコントロールのサイズを変更します。  
  
    -   上と横にあるサイズ変更ハンドルをドラッグすると、縦または横のサイズが変化します。  
  
    -   四隅にあるサイズ変更ハンドルをドラッグすると、縦横両方のサイズが変化します。  
  
    > [!TIP]
    >  Shift キーを押しながら→キーおよび↓キーを押すと、コントロールのサイズを 1 ダイアログ単位 \(DLU: Dialog Unit\) ずつ変更できます。  
  
### 内側にテキストが収まるようにコントロールのサイズを自動的に変更するには  
  
1.  \[書式\] メニューの \[テキストへのサイズ合わせ\] をクリックします。  
  
 または  
  
-   コントロールを右クリックし、ショートカット メニューの \[テキストへのサイズ合わせ\] をクリックします。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 要件  
  
 Win32  
  
## 参照  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)