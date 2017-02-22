---
title: "CCheckListBox クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCheckListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCheckListBox クラス"
  - "チェック リスト ボックス"
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CCheckListBox クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows のチェックリスト ボックスの機能を提供します。  
  
## 構文  
  
```  
  
class CCheckListBox : public CListBox  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CCheckListBox::CCheckListBox](../Topic/CCheckListBox::CCheckListBox.md)|`CCheckListBox` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CCheckListBox::Create](../Topic/CCheckListBox::Create.md)|Windows のチェックリスト ボックスを作成し、`CCheckListBox` のオブジェクトにアタッチします。|  
|[CCheckListBox::DrawItem](../Topic/CCheckListBox::DrawItem.md)|オーナー描画リスト ボックスの外観が変更されたときに、フレームワークによって呼び出されます。|  
|[CCheckListBox::Enable](../Topic/CCheckListBox::Enable.md)|チェックリスト ボックスの項目を有効または無効にします。|  
|[CCheckListBox::GetCheck](../Topic/CCheckListBox::GetCheck.md)|項目のチェック ボックスの状態を取得します。|  
|[CCheckListBox::GetCheckStyle](../Topic/CCheckListBox::GetCheckStyle.md)|コントロールのチェック ボックスのスタイルを取得します。|  
|[CCheckListBox::IsEnabled](../Topic/CCheckListBox::IsEnabled.md)|項目が有効かどうかを判定します。|  
|[CCheckListBox::MeasureItem](../Topic/CCheckListBox::MeasureItem.md)|オーナー描画スタイルのリスト ボックスが作成されるときに、フレームワークによって呼び出されます。|  
|[CCheckListBox::OnGetCheckPosition](../Topic/CCheckListBox::OnGetCheckPosition.md)|項目のチェック ボックスの位置を取得するために、フレームワークによって呼び出されます。|  
|[CCheckListBox::SetCheck](../Topic/CCheckListBox::SetCheck.md)|項目のチェック ボックスの状態を設定します。|  
|[CCheckListBox::SetCheckStyle](../Topic/CCheckListBox::SetCheckStyle.md)|コントロールのチェック ボックスのスタイルを設定します。|  
  
## 解説  
 「チェックリスト ボックスは」ファイル名のような項目の一覧を表示します。  ユーザーがオンまたはオフにできるリストの各項目には、その横にチェック ボックスがあります。  
  
 `CCheckListBox` は、オーナー描画コントロールに対してのみリストを文字列詳細が含まれているためです。  簡単に言うと、チェックリスト ボックスは、チェック ボックスが含まれますが、テキストを持つまったく必要はありません。  たとえば、各項目の横にチェック ボックスがある小さいビットマップの一覧を持つことができます。  
  
 独自のチェックリスト ボックスを作成するには、`CCheckListBox`から独自のクラスを派生させる必要があります。  独自のクラスを派生するには、派生クラスのコンストラクターと書き込み、**\[作成\]**を呼び出します。  
  
 親 \(通常は [CDialog](../../mfc/reference/cdialog-class.md)の派生クラス\) にリスト ボックスに送られた Windows の通知メッセージを処理するには、各メッセージの親クラスにメッセージ マップのエントリとメッセージ ハンドラー メンバー関数を追加します。  
  
 各メッセージ マップのエントリは次の形式を持ちます。  
  
 **ON\_**通知**\(**`id`、`memberFxn`**\)**  
  
 `id` が送信するコントロールの子ウィンドウ ID を指定します。`memberFxn` は、通知と通知を処理する、記述された親メンバー関数の名前です。  
  
 親の関数のプロトタイプは次のようになります。  
  
 **afx\_msg** `void` `memberFxn` **\( \);**  
  
 **CcheckListBox** を厳密に参照する 1 台のメッセージ マップ エントリがあります \(ただし [CListBox](../Topic/CListBox%20Class.md)については、メッセージ マップのエントリを参照\) :  
  
-   **ON\_CLBN\_CHKCHANGE** ユーザーは項目のチェック ボックスの状態を変更。  
  
 自分のチェックリスト ボックスが既定のチェックリスト ボックス \(それぞれの左側の既定サイズのチェック ボックスを持つ文字列の一覧\) の場合、チェック リスト ボックスを描画して、既定 [CCheckListBox::DrawItem](../Topic/CCheckListBox::DrawItem.md) を使用できます。  それ以外 [CListBox::CompareItem](../Topic/CListBox::CompareItem.md) 関数と [CCheckListBox::DrawItem](../Topic/CCheckListBox::DrawItem.md) と [CCheckListBox::MeasureItem](../Topic/CCheckListBox::MeasureItem.md) 関数をオーバーライドする必要があります。  
  
 ダイアログ テンプレートから直接またはコードのチェックリスト ボックスを作成できます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CListBox](../Topic/CListBox%20Class.md)  
  
 `CCheckListBox`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [MFC TSTCON サンプル](../../top/visual-cpp-samples.md)   
 [CListBox クラス](../Topic/CListBox%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CListBox クラス](../Topic/CListBox%20Class.md)