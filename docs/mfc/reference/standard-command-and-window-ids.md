---
title: "標準コマンド id とウィンドウ Id |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: d308f3f9efc5933124460d9839a0e94fffa60b4a
ms.lasthandoff: 02/24/2017

---
# <a name="standard-command-and-window-ids"></a>標準コマンド ID とウィンドウ ID
Microsoft Foundation Class ライブラリは、afxres.h 内でさまざまな標準のコマンドとウィンドウ Id を定義します。 これらの Id は、メッセージ ハンドラー関数をマッピングするリソース エディターと [プロパティ] ウィンドウ内で最もよく使用されます。 すべての標準コマンドが、 **id _**プレフィックス。 たとえば、メニュー エディターを使用するときに通常にバインドするファイルを開くメニュー項目、標準`ID_FILE_OPEN`コマンド ID  
  
 ほとんどの標準コマンドは、アプリケーション コード必要はありませんコマンド ID を参照するフレームワーク自体がその主な framework クラスのメッセージ マップをコマンドによって処理されるため ( `CWinThread`、 `CWinApp`、 `CView`、 **CDocument**など)。  
  
 プレフィックスである標準コマンド Id だけでなく他の標準的な Id の数が定義されての**AFX_ID**します。 これらの Id は、標準的なウィンドウの Id を含める (プレフィックス**afx_idw _**)、文字列の Id (プレフィックス**afx_ids _**)、およびその他のいくつかの型。  
  
 始まる Id を**AFX_ID**プログラマによってプレフィックスが使用されることはほとんどありませんが、参照することも framework 関数をオーバーライドする場合、これらの Id を参照する必要があります、 **AFX_ID**秒です。  
  
 Id がこのリファレンスで個別に記載されていません。 テクニカル ノートで、それらに関する詳細情報を記載できます[20](../../mfc/tn020-id-naming-and-numbering-conventions.md)、 [21](../../mfc/tn021-command-and-message-routing.md)、および[22](../../mfc/tn022-standard-commands-implementation.md)します。  
  
> [!NOTE]
>  (.Rc) ファイルは直接 Afxwin.h で含まれています。 次のステートメントは、アプリケーションのリソース スクリプト (.rc) ファイルに明示的に含める必要があります。  
  
 [!code-cpp[NVC_MFC_Utilities #&47;](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

