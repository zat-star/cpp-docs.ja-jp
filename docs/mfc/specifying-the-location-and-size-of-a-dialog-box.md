---
title: "Specifying the Location and Size of a Dialog Box | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "dialog boxes, size"
  - "dialog boxes, positioning"
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Specifying the Location and Size of a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ダイアログ ボックスの位置とサイズ、および含まれるコントロールの位置とサイズは、ダイアログ単位で表されます。  各コントロールとダイアログ ボックスの値は、選択時に Visual Studio のステータス バーの右下に表示されます。  
  
 [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)では、3 つのプロパティを設定して、ダイアログ ボックスが画面上で表示される位置を指定できます。  \[Center\] プロパティはブール型です。\[True\] に設定すると、ダイアログ ボックスは常に画面の中央に表示されます。  \[False\] に設定すると、\[Xpos\] プロパティと \[Ypos\] プロパティを設定して、ダイアログ ボックスが画面上で表示される位置を明示的に定義できます。  位置指定プロパティは表示領域の左上隅からのオフセット値であり、{X\=0, Y\=0} として定義されます。  また、位置は \[Absolute Align\] プロパティにも基づいています。このプロパティが \[True\] の場合、座標は画面を原点にした相対座標になり、\[False\] の場合はダイアログ ボックス オーナーのウィンドウを原点にした相対座標になります。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
## 要件  
 Win32  
  
## 参照  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)