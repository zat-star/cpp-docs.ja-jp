---
title: "ユーザー コントロールを MFC ビューとして Windows をホストしているフォーム |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms controls [C++], hosting as an MFC view
- hosting Windows Forms control [C++]
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7e4e0b7bc081d3b16b3f9aa55719d298f710cdab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="hosting-a-windows-forms-user-control-as-an-mfc-view"></a>MFC ビューとしての Windows フォーム ユーザー コントロールのホスト
MFC では、CWinFormsView クラスを使用して、Windows フォーム ユーザー コントロールを MFC ビューでホストします。 MFC Windows フォーム ビューは、ActiveX コントロールです。 ユーザー コントロールは、ネイティブのビューの子としてホストされ、ネイティブ ビューの全体のクライアント領域を占有します。  
  
 最終的な結果がによって使用されるモデルに似ています、 [CFormView クラス](../mfc/reference/cformview-class.md)です。 これは、操作により、機能豊富なフォーム ベースのビューを作成するには、Windows フォーム デザイナーとランタイムを活用できます。  
  
 MFC Windows フォーム ビューが ActiveX コントロールであるためがない同じ`hwnd`MFC ビューとして。 またへのポインターとして渡されることはできません、 [CView](../mfc/reference/cview-class.md)ビュー。 一般に、Windows フォーム ビューの操作を使用して Win32 にはそれほどに .NET Framework のメソッドを使用します。  
  
 MFC で使用される Windows フォームを表示するサンプル アプリケーションを参照してください。 [MFC と Windows フォーム統合](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法: ユーザー コントロールを作成し、MDI ビューをホストする](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)  
  
 [方法: Windows フォーム コントロールにコマンド ルーティングを追加する](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)  
  
 [方法: Windows フォーム コントロールのプロパティとメソッドを呼び出す](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)  
  
## <a name="see-also"></a>参照  
 [MFC における Windows フォーム ユーザー コントロールを使用します。](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [方法: 複合コントロールを作成する](/dotnet/framework/winforms/controls/how-to-author-composite-controls)