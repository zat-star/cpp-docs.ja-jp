---
title: "ウィザードのデザイン | Microsoft Docs"
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
  - "カスタム ウィザード [C++], デザイン (プロジェクトを)"
  - "プロジェクト [C++], カスタム ウィザード"
  - "Visual C++ プロジェクト, カスタム ウィザード"
  - "ウィザード [C++], カスタム"
ms.assetid: a7c0be7e-9297-4fed-83e3-5645c896d56b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ウィザードのデザイン
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ に用意されているアプリケーション ウィザードとは異なる、標準的な機能を備えたプロジェクトを作成する必要が生じる場合もあります。  そのような作業では、拡張やカスタマイズを簡単にできるようにデザインされた、Visual C\+\+ ウィザード アーキテクチャを使用できます。  ウィザードを作成するには、[Visual C\+\+ カスタム ウィザード](../ide/creating-a-custom-wizard.md)を使用します。  独自のウィザードを作成したら、プロジェクトに必要な初期ファイルを生成できるように、そのウィザードを構成します。  
  
 Visual C\+\+ のウィザードは HTML コントロールです。  このウィザードでは、<xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI.NavigateToCommandHandler%2A> や <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI.OkCancelAlert%2A> などの共通サービスを提供する、Visual C\+\+ ウィザード エンジン <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI> を使用します。  このウィザードではスクリプト エンジンも使用するため、VBScript と [JScript .NET](http://msdn.microsoft.com/ja-jp/c7e636ee-c10f-45b1-85ec-fe2daca30bf5) の両方を認識できます。  
  
 ウィザード アーキテクチャを使用すると、次のオブジェクト モデルにウィザードから直接アクセスしたり、これらのモデルのメソッド、プロパティ、およびイベントを JScript ファイルや HTML ファイルから呼び出したりできます。  詳細については、「[HTML ファイル](../ide/html-files.md)」および「[JScript ファイル](../ide/jscript-file.md)」の例を参照してください。  
  
-   [Visual Studio 環境の拡張](../Topic/Extending%20the%20Visual%20Studio%20Environment.md)  
  
-   [Visual C\+\+ コード モデル](http://msdn.microsoft.com/ja-jp/dd6452c2-1054-44a1-b0eb-639a94a1216b)  
  
-   [Visual C\+\+ プロジェクト モデル](http://msdn.microsoft.com/ja-jp/06c1bbd9-4c79-4f97-ad6d-2b1dea8ecd1f)  
  
-   [Visual C\+\+ ウィザード モデル](http://msdn.microsoft.com/ja-jp/159395ac-33c7-47bf-ad42-4e1435ddc758)  
  
 ウィザードのデザインの各要素については、「[ウィザード用に作成されるファイル](../ide/files-created-for-your-wizard.md)」を参照してください。  
  
## 参照  
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードをデザインする手順](../ide/steps-to-designing-a-wizard.md)   
 [ウィザードのカスタマイズ](../ide/customizing-your-wizard.md)