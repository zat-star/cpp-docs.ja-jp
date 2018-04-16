---
title: "コントロールのプロパティを編集 |Microsoft ドキュメント"
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
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls, editing properties
ms.assetid: 9bdae21d-6dec-4344-a197-2ca4fc46d040
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f2baed8431501bfa5bf68313403c87a1fb9bccb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="editing-control-properties"></a>コントロール プロパティの編集
### <a name="to-edit-the-properties-of-a-control-or-controls"></a>以上のコントロールのプロパティを編集するには  
  
1.  ダイアログ ボックスで、変更するコントロールを選択します。  
  
    > [!NOTE]
    >  複数のコントロールを選択した場合は、選択したコントロールに共通するプロパティのみを編集できます。  
  
2.  [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)コントロールのプロパティを変更します。  
  
    > [!NOTE]
    >  設定すると、**ビットマップ**ボタン、オプション ボタンまたはチェック ボックス コントロールと同じプロパティを**True**BS_BITMAP がコントロールの実装のスタイル。 詳細については、次を参照してください。[ボタン スタイル](../mfc/reference/styles-used-by-mfc.md#button-styles)です。 コントロールとビットマップの関連付けの例は、次を参照してください。 [CButton::SetBitmap](../mfc/reference/cbutton-class.md#setbitmap)です。 ビットマップは、ダイアログ リソース エディターでは、コントロールは表示されません。  
  
### <a name="to-undo-changes-to-the-properties-of-a-control"></a>コントロールのプロパティへの変更を元に戻す  
  
1.  ダイアログ エディターで、コントロールにフォーカスがあることを確認してください。  
  
2.  選択**を元に戻す**から、**編集**メニュー (フォーカスがコントロール上にない場合、**を元に戻す**コマンドは使用できません)。  
  
 マネージ プロジェクトにリソースを追加する方法については、次を参照してください。[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* 」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「 [チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) 」および「 [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)。  
  
 必要条件  
  
 Win32  
  
## <a name="see-also"></a>参照  
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)

