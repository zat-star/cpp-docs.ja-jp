---
title: "ダイアログ ボックス コントロールとコード間の切り替え |Microsoft ドキュメント"
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
- events [C++], viewing for controls
- Windows messages [C++], controls
- messages [C++], viewing for dialog boxes
- Dialog editor, accessing code
- code [C++], switching from Dialog Editor
- controls [C++], jumping to code
- Dialog editor, switching between controls and code
ms.assetid: 7da73815-b853-4203-ba45-bbe570695122
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 81f8ea53cf6c4428913ce7ebfa4183c135208024
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="switching-between-dialog-box-controls-and-code"></a>ダイアログ ボックス コントロールとコード間の切り替え
MFC アプリケーションで、ハンドラーのコードに移動する、またはハンドラー関数スタブをすばやく作成するためのダイアログ ボックス コントロールをダブルクリックすることができます。  
  
 クリックするコントロールを選択し、**イベント コントロール**ボタンまたは**メッセージ**ボタンをクリックして、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)Windows メッセージおよびイベントの完全な一覧を表示するには選択した項目に使用できます。 ハンドラー関数を作成または更新リストから選択します。  
  
### <a name="to-jump-to-code-from-the-dialog-editor"></a>ダイアログ エディターからコードに移動するには  
  
1.  最後に実装されたメッセージの処理関数の宣言に移動する ダイアログ ボックス内のコントロールをダブルクリックします。 (ATL ベースのダイアログ クラスでは、常にジャンプするコンス トラクターの定義にします。)  
  
### <a name="to-view-events-for-a-control"></a>コントロールのイベントを表示するには  
  
1.  クリックするコントロールを選択し、**イベント コントロール**ボタンをクリックして、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。  
  
    > [!NOTE]
    >  クリックすると、**イベント コントロール**ボタン、  *ダイアログ ボックス* ダイアログ ボックスを展開すると、各コントロールのイベントを編集するフォーカス公開のすべてのコントロールの一覧があります。  
  
     1 つのコントロールがあるフォーカスを使用 ダイアログ ボックスで、ときに、右クリックし、選択**イベント ハンドラーの追加**ショートカット メニューからです。 これにより、ハンドラーを追加するクラスを指定することができます。 詳細については、次を参照してください。[イベント ハンドラーを追加する](../ide/adding-an-event-handler-visual-cpp.md)です。  
  
### <a name="to-view-messages-for-a-dialog-box"></a>メッセージ ダイアログ ボックスを表示するには  
  
1.  ダイアログ ボックスをオン をクリックして、**メッセージ**ボタンをクリックして、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 必要条件  
  
 Win32  
  
## <a name="see-also"></a>参照  
 [ダイアログ エディター](../windows/dialog-editor.md)

