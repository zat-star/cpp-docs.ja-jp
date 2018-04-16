---
title: "メニューとメニュー コマンド移動およびコピー |Microsoft ドキュメント"
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
- commands, copying on menus
- menu items, moving
- commands, moving on menus
- menu items, copying
ms.assetid: 1d8df535-9922-4579-a9c2-37aeac1856eb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d6042647d0eff213dae82440b9733cff64e94631
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="moving-and-copying-menus-and-menu-commands"></a>メニューとメニュー コマンドの移動およびコピー
ドラッグ アンド ドロップ操作またはショートカット メニュー (右クリック メニュー) のコマンドを使用して、メニューとメニュー コマンドを移動またはコピーすることができます。  
  
### <a name="to-move-or-copy-menus-or-menu-commands-using-the-drag-and-drop-method"></a>ドラッグ アンド ドロップ操作を使用してメニューやメニュー コマンドを移動またはコピーするには  
  
1.  移動する項目を次の場所にドラッグまたはコピーします。  
  
    -   現在のメニュー上の新しい場所。  
  
    -   別のメニュー (他のメニューに移動するには、そのメニューにマウス ポインターをドラッグします)。  
  
2.  挿入ガイドで目的の位置が示されたら、メニュー コマンドをドロップします。  
  
### <a name="to-move-or-copy-menus-or-menu-commands-using-shortcut-menu-commands"></a>ショートカット メニューのコマンドを使用してメニューやメニュー コマンドを移動またはコピーするには  
  
1.  1 つ以上のメニューまたはメニュー コマンドを右クリックします。  
  
2.  ショートカット メニューの **[切り取り]** (移動する場合) または **[コピー]**を選択します。  
  
3.  項目を別のメニュー リソース ファイルまたはリソース スクリプト ファイルに移動する場合は、 [そのファイルを別のウィンドウで開きます](/visualstudio/ide/customizing-window-layouts-in-visual-studio)。  
  
4.  メニューやメニュー コマンドを移動またはコピーする位置を選択します。  
  
5.  ショートカット メニューの **[貼り付け]**を選択します。 移動またはコピーする項目は、選択した項目の前に配置されます。  
  
    > [!NOTE]
    >  ドラッグでコピーした項目を別のメニュー ウィンドウの別のメニューに貼り付けることもできます。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* 」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「 [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)を選択します。  
  
 **必要条件**  
  
 Win32  
  
## <a name="see-also"></a>参照  
 [メニュー エディター](../windows/menu-editor.md)