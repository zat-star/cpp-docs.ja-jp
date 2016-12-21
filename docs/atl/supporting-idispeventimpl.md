---
title: "IDispEventImpl のサポート | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDispEventImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, IDispEventImpl サポート (COM オブジェクトの)"
  - "BEGIN_SINK_MAP マクロ"
  - "イベント シンク マップ, 宣言"
  - "IDispEventImpl クラス, アドバイズとアドバイズ中止"
  - "IDispEventImpl クラス, 宣言"
  - "SINK_ENTRY マクロ"
  - "タイプ ライブラリ, インポート"
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDispEventImpl のサポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレート クラス [IDispEventImpl](../atl/reference/idispeventimpl-class.md) が ATL クラスのコネクション ポイント シンクをサポートするために使用できます。  外部 COM オブジェクトから発生した接続ポイント シンクは、クラスのイベントを処理できます。  これらのコネクション ポイント シンクはイベント シンク マップと、クラスにマップされます。  
  
 正しくクラスのコネクション ポイント シンクを実行するには、以下の手順を実行する必要があります:  
  
-   各外部オブジェクトのタイプ ライブラリをインポート  
  
-   `IDispEventImpl` のインターフェイスを宣言します。  
  
-   イベント シンク マップを宣言します。  
  
-   unadvise コネクション ポイントするとアドバイス  
  
 コネクション ポイント シンクすべて実行に関連する手順は、クラスのヘッダー ファイルだけです \(.h\) 変更します。  
  
## タイプ ライブラリのインポート  
 、処理するイベント タイプ ライブラリをインポートする必要のある各外部オブジェクトに対して。  この手順では、処理できる定義し、使用する情報を提供するイベントをイベント シンク マップを宣言するとき。  [\#import](../Topic/%23import%20Directive%20\(C++\).md) ディレクティブが、を使用できます。  では、クラスのヘッダー ファイルにサポートする各ディスパッチ インターフェイスの `#import` の必要なディレクティブの行を追加します \(.h\)。  
  
 次の例は、外部 COM サーバー \(`MSCAL.Calendar.7`\) のタイプ ライブラリをインポート:  
  
 [!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/CPP/supporting-idispeventimpl_1.h)]  
  
> [!NOTE]
>  でサポートする各外部タイプ ライブラリの `#import` にステートメントが必要です。  
  
## IDispEventImpl インターフェイスの宣言  
 各ディスパッチ インターフェイスのタイプ ライブラリをインポートするため、各外部ディスパッチ インターフェイスの `IDispEventImpl` の別のインターフェイスを宣言する必要があります。  各外部オブジェクトの `IDispEventImpl` のインターフェイス宣言を追加することで、クラスの宣言を変更します。  パラメーターの詳細については、[IDispEventImpl](../atl/reference/idispeventimpl-class.md)を参照してください。  
  
 次のコードでは、2 とおりのコネクション ポイント シンク、`DCalendarEvents` インターフェイスに `CMyCompositCtrl2`、クラスで実装される COM オブジェクトを宣言します:  
  
 [!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/CPP/supporting-idispeventimpl_2.h)]  
  
## イベント シンク マップの宣言  
 適切な関数が処理されるイベント通知のためのクラスは、正しいハンドラーに各イベントを転送する必要があります。  これは、イベント シンク マップの宣言により実行されます。  
  
 ATL は、このマッピングを容易にするいくつかのマクロ、[BEGIN\_SINK\_MAP](../Topic/BEGIN_SINK_MAP.md)、[END\_SINK\_MAP](../Topic/END_SINK_MAP.md)と [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY.md)を提供します。  標準形式は次のとおりです。:  
  
 `BEGIN_SINK_MAP(comClass)`  
  
 `SINK_ENTRY_EX(id, iid, dispid, func)`  
  
 `.  .  .  //additional external event entries`  
  
 `END_SINK_MAP()`  
  
 次の例では、2 人のイベント ハンドラーを持つイベント シンク マップを宣言します:  
  
 [!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/CPP/supporting-idispeventimpl_3.h)]  
  
 実装はほぼ完了です。  最後に、外部インターフェイスの表示と unadvising の問題です。  
  
## アドバイズと Unadvising IDispEventImpl のインターフェイス  
 最後の手順は、必要なときに \(または\) unadvise すべてのコネクション ポイントに指示するメソッドを実装することです。  アドバイズするこれは、外部クライアントすると、オブジェクト間の通信の前にされていない場合に発生します。  、オブジェクトが表示されるようになる前に、オブジェクトによってサポートされる各外部ディスパッチ インターフェイスは、アウトゴーイング インターフェイスに問い合わせます。  接続が確立され、オブジェクトからのイベントを処理するためにアウトゴーイング インターフェイスへの参照が使用されます。  この手順は、「」と表示されます。  
  
 、オブジェクトが外部インターフェイスと終了すると、アウトゴーイング インターフェイスは、クラスによっても使用されていないことを把握する必要があります。  このプロセスは「」と呼ばれ unadvising。  
  
 COM オブジェクトの一意な性質については、この手順では、実装の間で、詳細実行、異なるため。  これらの詳細は、このトピックの範囲を超えるあり、アドレス。  
  
## 参照  
 [ATL COM オブジェクトの基本事項](../atl/fundamentals-of-atl-com-objects.md)