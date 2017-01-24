---
title: "手動でコントロールを追加する方法 | Microsoft Docs"
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
  - "コモン コントロール [C++], 追加"
  - "制御 (入力フォーカスを)"
  - "コントロール [MFC], 追加 (ダイアログ ボックスに)"
  - "ダイアログ ボックス コントロール [C++], 追加 (ダイアログ ボックスに)"
  - "フォーカス, 制御 (入力を)"
  - "入力フォーカス コントロール"
  - "Windows コモン コントロール [C++], 追加"
ms.assetid: bc843e59-0c51-4b5b-8bf2-343f716469d2
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 手動でコントロールを追加する方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コード内 [ダイアログ エディターを使用してダイアログ ボックスにコントロールを追加します。](../mfc/using-the-dialog-editor-to-add-controls.md) または追加する独自、できます。  
  
 コントロール オブジェクトを独自に作成するには、通常、. C\+\+ ダイアログまたはフレーム ウィンドウ オブジェクトに C\+\+ コントロール オブジェクトを埋め込みます。  フレームワークの他のオブジェクトと同様に、コントロールは正常な構築式が必要です。  親ダイアログ ボックスまたはフレーム ウィンドウの作成時にコントロールの **作成** のメンバー関数を呼び出す必要があります。  ダイアログ ボックスでは、これは通常 [OnInitDialog](../Topic/CDialog::OnInitDialog.md)、[OnCreate](../Topic/CWnd::OnCreate.md)のフレーム ウィンドウに表示されます。  
  
 どのように派生ダイアログ クラスのクラス宣言の `CEdit` オブジェクトを宣言し、`OnInitDialog`の **作成** のメンバー関数を呼び出す方法を次の例に示します。  `CEdit` オブジェクトは埋め込みオブジェクトとして宣言されているので、ダイアログ オブジェクトの構築、**作成** 独自のメンバー関数と初期化されなければなりませんと自動的に生成されます。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#1](../mfc/codesnippet/CPP/adding-controls-by-hand_1.h)]  
  
 `OnInitDialog` の次の関数は、四角形を設定し、Windows のエディット コントロールを作成し、`CEdit` の初期化されていないオブジェクトにアタッチします。**作成** を呼び出します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#2](../mfc/codesnippet/CPP/adding-controls-by-hand_2.cpp)]  
  
 編集オブジェクトを作成した後に、コントロールに `SetFocus` メンバー関数を呼び出すことで、入力フォーカスを設定できます。  最後に、`OnInitDialog` からフォーカスを設定できないことを示すには、0 を返します。  0 以外の値を返した場合、ダイアログ マネージャーは、ダイアログ コントロール項目リストの最初の項目にフォーカスを設定します。  ほとんどの場合は、ダイアログ エディターを使用してダイアログ ボックスにコントロールを追加する必要があります。  
  
## 参照  
 [コントロールの作成方法と使い方](../mfc/making-and-using-controls.md)   
 [コントロール](../mfc/controls-mfc.md)   
 [CDialog::OnInitDialog](../Topic/CDialog::OnInitDialog.md)