---
title: "方法: メッセージ マップ クロス リファレンスの使い方 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: ffa7b39962d78476e971750e92569eb14229606b
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="how-to-use-the-message-map-cross-reference"></a>メッセージ マップ クロス リファレンスの使い方
ラベル付きのエントリで\<memberFxn >、派生クラス用の独自のメンバー関数を記述[CWnd](../../mfc/reference/cwnd-class.md)クラスです。 関数の任意の名前を付けます。 などの他の関数`OnActivate`、クラスのメンバー関数は、`CWnd`です。 メッセージを通過するときに呼び出されると、 `DefWindowProc` Windows の機能です。 Windows の通知メッセージを処理するには、上書き、対応する`CWnd`派生クラスで関数。 関数は、基本クラスを基本クラスでオーバーライドされた関数を呼び出す必要があり、Windows がメッセージに応答します。  
  
 すべての場合に、関数プロトタイプ、 `CWnd`-派生クラスのヘッダー、およびコード メッセージ マップ エントリが示すようにします。  
  
 次の用語が使用されます。  
  
|用語|定義|  
|----------|----------------|  
|ID|いずれかのユーザー定義メニュー項目の ID (**WM_COMMAND**メッセージ) または ID (子ウィンドウの通知メッセージ) を制御します。|  
|"message"と"wNotifyCode"|Windows では、WINDOWS で定義されている Id がメッセージします。H.|  
|nMessageVariable|戻り値を格納する変数の名前、**を通じて**Windows の機能です。|  
  
## <a name="see-also"></a>関連項目  
 [メッセージ マップ](../../mfc/reference/message-maps-mfc.md)


