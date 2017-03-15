---
title: "MFC ダイアログ ボックスにおける Windows フォーム ユーザー コントロールのホスト | Microsoft Docs"
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
  - "ホスト (Windows フォーム コントロールを) [C++]"
  - "MFC [C++], Windows フォームのサポート"
  - "Windows フォーム [C++], MFC サポート"
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# MFC ダイアログ ボックスにおける Windows フォーム ユーザー コントロールのホスト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC は、Windows フォーム コントロールを特殊な ActiveX コントロールとしてホストし、ActiveX インターフェイス、および <xref:System.Windows.Forms.Control> クラスのプロパティやメソッドを使用してそのコントロールと通信します。  コントロールを操作するには、.NET Framework のプロパティやメソッドを使用することをお勧めします。  
  
 Windows フォームと MFC の組み合わせ示すサンプル アプリケーションについては、["MFC and Windows Forms Integration \(MFC Windows フォームとの統合\)"](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)を参照してください。  
  
> [!NOTE]
>  現在のリリースでは、`CDialogBar`  オブジェクトは Windows フォーム コントロールをホストできません。  
  
## このセクションの内容  
 [方法: ダイアログ ボックスにユーザー コントロールおよびホストを作成する](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)  
  
 [方法: Windows フォームで DDX\/DDV データ バインドを実行する](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)  
  
 [方法: ネイティブ C\+\+ クラスから Windows フォーム イベントをシンクする](../Topic/How%20to:%20Sink%20Windows%20Forms%20Events%20from%20Native%20C++%20Classes.md)  
  
## 関連項目  
 [CWinFormsControl クラス](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog クラス](../mfc/reference/cdialog-class.md) &#124; [CWnd クラス](../Topic/CWnd%20Class.md) &#124; <xref:System.Windows.Forms.Control>  
  
## 参照  
 [MFC での Windows フォーム ユーザー コントロールの使用](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Windows フォームと MFC のプログラミング上の違い](../dotnet/windows-forms-mfc-programming-differences.md)   
 [MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [MFC ダイアログ ボックスとしての Windows フォーム ユーザー コントロールのホスト](../Topic/Hosting%20a%20Windows%20Form%20User%20Control%20as%20an%20MFC%20Dialog%20Box.md)