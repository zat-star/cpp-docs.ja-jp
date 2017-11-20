---
title: "MFC アプリケーションのステータス バーのテキストとメニュー コマンドの関連付け |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- status bars, associating menu items
- menus, status bar text
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 16bf93390538a5f2abebb2bf327970dbec1d2a8b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="associating-menu-commands-with-status-bar-text-in-mfc-applications"></a>メニュー コマンドと MFC アプリケーションのステータス バーのテキストとの関連付け
アプリケーションでは、ユーザーが選択する各メニュー コマンドに対して、説明のテキストを表示できます。 そのためには、[プロパティ] ウィンドウの **[プロンプト]** プロパティを使用し、各メニュー コマンドにテキスト文字列を割り当てます。 コマンドと同じ ID を持つ [ストリング テーブル](../windows/string-editor.md) に文字列がある場合、MFC アプリケーションでは、ユーザーがマウス ポインターをメニュー項目の上に置くと、実行中のアプリケーションのステータス バーにこの文字列リソースが自動的に表示されます。  
  
### <a name="to-associate-a-menu-command-with-a-status-bar-text-string"></a>メニュー コマンドをステータス バーのテキスト文字列に関連付けるには  
  
1.  **メニュー** エディターで、メニュー コマンドを選択します。  
  
2.  [[プロパティ] ウィンドウ](/visualstudio/ide/reference/properties-window)で、関連付けるステータス バーのテキストを **[プロンプト]** ボックスに入力します。  
  

  
 **必要条件**  
  
 MFC  
  
## <a name="see-also"></a>関連項目  
 [文字列 (ATL と MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [メニューにコマンドを追加します。](../windows/adding-commands-to-a-menu.md)   
 [メニュー エディター](../windows/menu-editor.md)