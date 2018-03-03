---
title: "MFC ダイアログ ボックスでユーザー コントロールをフォーム、Windows をホストしている |Microsoft ドキュメント"
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
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: da8e8a54947b329fe36eea5c80bdc13ba5cdfa74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>MFC ダイアログ ボックスにおける Windows フォーム ユーザー コントロールのホスト
MFC ActiveX コントロールの特別な種類の Windows フォーム コントロールをホストし、ActiveX インターフェイス、およびのプロパティとメソッドを使用して、コントロールと通信、<xref:System.Windows.Forms.Control>クラスです。 コントロール上で動作する .NET Framework のプロパティとメソッドを使用することをお勧めします。  
  
 MFC で使用される Windows フォームを表示するサンプル アプリケーションを参照してください。 [MFC と Windows フォーム統合](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)です。  
  
> [!NOTE]
>  現在のリリースで、`CDialogBar`オブジェクトは、Windows フォーム コントロールをホストできません。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法: ダイアログ ボックスにユーザー コントロールおよびホストを作成する](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)  
  
 [方法: Windows フォームで DDX/DDV データ バインディングの操作を行います](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)  
  
 [方法: ネイティブ C++ クラスから Windows フォーム イベントをシンクする](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)  
  
## <a name="reference"></a>参照  
 [関数クラス](../mfc/reference/cwinformscontrol-class.md)&#124;です。[CDialog クラス](../mfc/reference/cdialog-class.md)&#124;です。[CWnd クラス](../mfc/reference/cwnd-class.md)&#124;です。<xref:System.Windows.Forms.Control>  
  
## <a name="see-also"></a>参照  
 [MFC における Windows フォーム ユーザー コントロールを使用します。](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Windows フォームと MFC プログラミング上の違い](../dotnet/windows-forms-mfc-programming-differences.md)   
 [MFC ビューとして Windows フォーム ユーザー コントロールをホストしています。](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [MFC ダイアログ ボックスとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)