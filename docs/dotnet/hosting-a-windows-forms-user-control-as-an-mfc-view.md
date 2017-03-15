---
title: "MFC ビューとしての Windows フォーム ユーザー コントロールのホスト | Microsoft Docs"
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
  - "Windows フォーム コントロール [C++], ホスト (MFC ビューとして)"
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# MFC ビューとしての Windows フォーム ユーザー コントロールのホスト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC は、CWinFormsView クラスを使用して、MFC ビューで Windows フォームのユーザー コントロールをホストします。  MFC の Windows フォーム ビューは ActiveX コントロールです。  ユーザー コントロールは、ネイティブ ビューの子としてホストされ、ネイティブ ビューのクライアント領域全体を占有します。  
  
 最終的には、[CFormView クラス](../mfc/reference/cformview-class.md)で使用されるモデルのようになります。  これにより、Windows フォーム デザイナーとランタイムを利用して、リッチなフォーム ベースのビューを作成できます。  
  
 MFC の Windows フォーム ビューは ActiveX コントロールなので、MFC ビューと同じ `hwnd` は使用しません。  また、このビューをポインターとして [CView](../Topic/CView%20Class.md) ビューを渡すこともできません。  一般に、Windows フォーム ビューを使用し、Win32 にあまり依存しないようにするには、.NET Framework のメソッドを使用します。  
  
 Windows フォームと MFC の組み合わせ示すサンプル アプリケーションについては、["MFC and Windows Forms Integration \(MFC Windows フォームとの統合\)"](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)を参照してください。  
  
## このセクションの内容  
 [方法: ユーザー コントロールを作成し、MDI ビューをホストする](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)  
  
 [方法: Windows フォーム コントロールにコマンド ルーティングを追加する](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)  
  
 [方法: Windows フォーム コントロールのプロパティとメソッドを呼び出す](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)  
  
## 参照  
 [MFC での Windows フォーム ユーザー コントロールの使用](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [方法 : 複合コントロールを作成する](../Topic/How%20to:%20Author%20Composite%20Controls.md)