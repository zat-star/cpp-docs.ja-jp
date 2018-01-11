---
title: "OLE コモン ダイアログ クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.ole
dev_langs: C++
helpviewer_keywords:
- ActiveX classes [MFC]
- dialog classes [MFC], OLE
- OLE common dialog classes [MFC]
- common dialog classes [MFC]
ms.assetid: 706526ae-f94f-4909-a0f8-6b5fe954fd97
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0617354337e75e2c2431df894c054722349e2306
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ole-common-dialog-classes"></a>OLE コモン ダイアログ クラス
これらのクラスは、いくつかの標準の OLE ダイアログ ボックスを実装することで、OLE の一般的なタスクを処理します。 OLE の機能の一貫性のあるユーザー インターフェイスも提供します。  
  
 [関数](../mfc/reference/coledialog-class.md)  
 OLE ダイアログ ボックスをすべての一般的な実装を含むため、フレームワークで使用します。 ユーザー インターフェイスのカテゴリ内のすべてのダイアログ ボックス クラスは、この基本クラスから派生します。 `COleDialog`直接使用することはできません。  
  
 [メンバー](../mfc/reference/coleinsertdialog-class.md)  
 リンクまたは埋め込みアイテムの新しい OLE を挿入するは、オブジェクトの挿入 ダイアログ ボックスで、標準のユーザー インターフェイスを表示します。  
  
 [関数](../mfc/reference/colepastespecialdialog-class.md)  
 貼り付け ダイアログ ボックス、編集貼り付け コマンドを実装するための標準のユーザー インターフェイスを表示します。  
  
 [関数](../mfc/reference/colelinksdialog-class.md)  
 リンクの編集 ダイアログ ボックスで、リンクされた項目に関する情報を変更するための標準のユーザー インターフェイスを表示します。  
  
 [メンバー](../mfc/reference/colechangeicondialog-class.md)  
 アイコンの変更 ダイアログ ボックスで、OLE に関連付けられているアイコンの埋め込みを変更、またはリンクされた項目のための標準のユーザー インターフェイスを表示します。  
  
 [メンバー](../mfc/reference/coleconvertdialog-class.md)  
 OLE 項目を別の 1 つの型に変換する標準のユーザー インターフェイスである [変換] ダイアログ ボックスが表示されます。  
  
 [メンバー](../mfc/reference/colepropertiesdialog-class.md)  
 Windows コモン OLE プロジェクト プロパティ ダイアログ ボックスをカプセル化します。 共通の OLE プロパティ ダイアログ ボックスでは、表示し、Windows の標準に準拠した形式での OLE ドキュメント項目のプロパティを変更する簡単な方法を提供します。  
  
 [関数](../mfc/reference/coleupdatedialog-class.md)  
 更新プログラム ダイアログ ボックスで、ドキュメント内のすべてのリンクを更新するための標準のユーザー インターフェイスを表示します。 ダイアログ ボックスには、完了するまで更新手順は、どの程度近いかを示すために、進行状況インジケーターが含まれています。  
  
 [メンバー](../mfc/reference/colechangesourcedialog-class.md)  
 ソースの変更 ダイアログ ボックスで、移行先やリンクのソースを変更する標準のユーザー インターフェイスを表示します。  
  
 [COleBusyDialog](../mfc/reference/colebusydialog-class.md)  
 サーバーがビジー状態、サーバーが応答していないダイアログ ボックス、ビジー状態のアプリケーションへの呼び出しを処理するための標準のユーザー インターフェイスを表示します。 通常、によって自動的に表示されます、`COleMessageFilter`実装します。  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../mfc/class-library-overview.md)

