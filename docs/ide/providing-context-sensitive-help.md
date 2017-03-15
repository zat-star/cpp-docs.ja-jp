---
title: "状況依存のヘルプの指定 | Microsoft Docs"
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
  - "状況依存のヘルプ"
  - "状況依存のヘルプ, カスタム ウィザード"
  - "カスタム ウィザード, 実装 (ヘルプを)"
ms.assetid: c6c4d961-29d3-4d16-9f39-b12545aba540
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 状況依存のヘルプの指定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[カスタム ウィザード](../Topic/Application%20Settings,%20Custom%20Wizard.md)で作成したウィザードには、\[ヘルプ\] ボタンが挿入されます。  
  
 プロジェクトの各 .htm ファイルには、ウィザードの \[ヘルプ\] ボタンをサポートするための次のコードが含まれています。  
  
```  
<BUTTON CLASS="BUTTONS" ID="HelpBtn" ACCESSKEY="H"  
 onClick="window.external.OnHelp('vc.appwiz.custom.overview');">  
```  
  
 <xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.OnHelp%2A> によって、ウィザードの該当ページに関連付けられている HTML ヘルプ ファイルのキーワードが指定されます。  HTML ヘルプ ファイルを作成してページに関連付ける方法については、「[HTML Help Start Page](vsconhh1start)」を参照してください。  このウィザード ページに対して独自のヘルプを指定するには、文字列 `'vc.appwiz.custom.overview'` をそのページの HTML ヘルプ トピックを識別するキーワードに置き換える必要があります。  
  
 **メモ** この .htm ファイルは、コンパイル済みの MSDN ヘルプには統合できません。  
  
## 参照  
 [ウィザード用に作成されるファイル](../ide/files-created-for-your-wizard.md)   
 [カスタム ウィザード](../ide/custom-wizard.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)