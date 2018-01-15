---
title: "水平スクロール バーの幅の設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- list controls, scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars, displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars, width
ms.assetid: 51dad141-aa0b-46a3-a82c-46b80d603d94
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7aeabed9eaa164a0c19fd6b425f36e68059a548d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setting-the-width-of-a-horizontal-scroll-bar"></a>水平スクロール バーの幅の設定
MFC クラスを使用してダイアログ ボックスに水平スクロール バーをリスト ボックスを追加すると、スクロール バーは、アプリケーションでは自動的に表示されません。  
  
### <a name="to-make-the-scroll-bar-appear"></a>スクロール バーを表示する  
  
1.  呼び出して最も幅の広い要素の最大の幅を設定[CListBox::SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent)コードにします。  
  
     この値を設定せず、スクロール バーは表示されません、でも、リスト ボックス内の項目は、ボックスよりも太くなってとき。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 必要条件  
  
 MFC  
  
## <a name="see-also"></a>参照  
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)

