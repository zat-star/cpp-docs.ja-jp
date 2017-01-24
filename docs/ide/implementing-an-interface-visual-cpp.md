---
title: "インターフェイスの実装 (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "インターフェイス, 実装"
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# インターフェイスの実装 (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

インターフェイスを実装するには、プロジェクトを ATL COM アプリケーションまたは ATL サポートを持つ MFC アプリケーションとして作成しておく必要があります。  [ATL プロジェクト ウィザード](../Topic/ATL%20Project%20Wizard.md)を使用して ATL アプリケーションを作成するか、または [MFC アプリケーションに ATL オブジェクトを追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)して MFC アプリケーション用の ATL サポートを実装できます。  
  
 プロジェクトを作成したら、インターフェイスを実装するために、まず ATL オブジェクトを追加します。  オブジェクトを ATL プロジェクトに追加するウィザードの一覧については、「[ATL プロジェクトへのオブジェクトとコントロールの追加](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)」を参照してください。  
  
> [!NOTE]
>  このウィザードでは、ATL ダイアログ、ATL を使用する XML Web サービス、パフォーマンス オブジェクト、およびパフォーマンス カウンターはサポートされていません。  
  
 [ATL コントロールを追加](../atl/reference/adding-an-atl-control.md)する場合は、atlcom.h で定義されており、ウィザードの [&#91;インターフェイス&#93;](../atl/reference/interfaces-atl-control-wizard.md) ページにある既定のインターフェイスを実装するかどうかを指定できます。  
  
 オブジェクトまたはコントロールを追加したら、インターフェイス実装ウィザードを使用して、利用できるタイプ ライブラリ内のその他のインターフェイスを実装できます。  
  
 新しいインターフェイスは、プロジェクトの .idl ファイルに手動で追加する必要があります。  詳細については、「[ATL プロジェクトでの新しいインターフェイスの追加](../Topic/Adding%20a%20New%20Interface%20in%20an%20ATL%20Project.md)」を参照してください。  
  
### インターフェイスを実装するには  
  
1.  クラス ビューで、ATL オブジェクトのクラス名を右クリックします。  
  
2.  ショートカット メニューの \[追加\] をクリックしてから、**\[インターフェイスの実装\]** をクリックして[インターフェイス実装ウィザード](../Topic/Implement%20Interface%20Wizard.md)を表示します。  
  
3.  実装するインターフェイスを該当するタイプ ライブラリから選択し、\[完了\] をクリックします。  
  
4.  クラス ビューで、オブジェクトの \[ベースとインターフェイス\] ノードを展開して実装したインターフェイスを表示し、さらにインターフェイスのノードを展開して使用できるプロパティ、メソッド、およびイベントを表示します。  
  
    > [!NOTE]
    >  [オブジェクト ブラウザー](http://msdn.microsoft.com/ja-jp/f89acfc5-1152-413d-9f56-3dc16e3f0470)は、インターフェイスのメンバーを確認するために使用することもできます。  
  
## 参照  
 [COM インターフェイスの作成](../ide/creating-a-com-interface-visual-cpp.md)   
 [COM インターフェイスの編集](../ide/editing-a-com-interface.md)