---
title: "RDO RemoteData コントロールでデータを更新する | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RDO RemoteData コントロール"
  - "RDO RemoteData コントロール, 更新 (データを)"
  - "RemoteData コントロール"
  - "RemoteData コントロール, 更新 (データを)"
ms.assetid: abb4175f-612e-4645-905e-c0fa918b0fd7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RDO RemoteData コントロールでデータを更新する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

RDO RemoteData コントロールのデータは、読み取り専用にすることも、変更可能にすることもできます。  
  
### RDO RemoteData コントロールを使用してデータを変更するアプリケーションを作成するには  
  
1.  RDO RemoteData コントロールの **CursorDriver** プロパティを設定します。  
  
    -   Server Side カーソルは、返されたデータをサーバーに格納します。  
  
    -   ODBC Client Side カーソルは、データをクライアントのローカル ストレージに格納します。  
  
    -   Client Batch Side カーソルは、並列処理用のカーソル ライブラリを使用します。  
  
    -   アクション クエリの実行時は Cursor オプションが使用されません。したがって、カーソルは不要です。  
  
2.  RDO RemoteData コントロールの **LockType** プロパティを設定します。  結果セット オプションに基づくオプティミスティック同時実行制御をお勧めします。  
  
    -   Read\-only concurrency オプションを使用しないでください。  
  
    -   Pessimistic concurrency オプションでは、更新中のデータがロックされます。したがって、他のユーザーはデータ変更をコミットできません。  
  
    -   Optimistic concurrency オプションでは、データがロックされません。ただし、コミット中にほかのクライアントによってデータが更新され矛盾した状態が発生すると、RDO RemoteData コントロールがエラーを検出してスローします。  
  
3.  RDO RemoteData コントロールの **ResultsetType** プロパティを設定します。  選択したオプションが ODBC ドライバーでサポートされていることを確認してください。  
  
    -   \[Create Static Cursor\] をクリックすると、カーソルをいったん閉じ、再度開くまで、変更が検出されません。  
  
    -   \[Create Keyset Cursor\] をクリックすると、キーセット カーソル内で自由に挿入、更新、および削除を行うことができます。  
  
4.  必要に応じて、データ バインド コントロールを更新可能に設定します。  更新可能にできないコントロールもあります。  
  
 これらのオブジェクトの使用方法については、RDO RemoteData コントロールに関するドキュメントを参照してください。  
  
## 参照  
 [RDO データ バインド](../../data/ado-rdo/rdo-databinding.md)   
 [Visual C\+\+ で RDO データ バインドを使用する](../../data/ado-rdo/using-rdo-databinding-in-visual-cpp.md)