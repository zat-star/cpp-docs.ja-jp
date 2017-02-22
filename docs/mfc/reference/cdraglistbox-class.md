---
title: "CDragListBox クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDragListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDragListBox クラス"
  - "ドラッグ リスト ボックス [C++]"
  - "ドラッグ (リスト項目を)"
  - "リスト ボックス"
  - "Windows [C++], リスト ボックス"
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CDragListBox クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows のリスト ボックスの機能に加えて、`CDragListBox` クラスはユーザーがリスト ボックスの項目を、リスト ボックス内のファイル名など実行できるようにします。  
  
## 構文  
  
```  
class CDragListBox : public CListBox  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDragListBox::CDragListBox](../Topic/CDragListBox::CDragListBox.md)|`CDragListBox` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDragListBox::BeginDrag](../Topic/CDragListBox::BeginDrag.md)|フレームワークによって呼び出されたときにドラッグ操作を開始します。|  
|[CDragListBox::CancelDrag](../Topic/CDragListBox::CancelDrag.md)|ドラッグ操作がキャンセルされたときに、フレームワークによって呼び出されます。|  
|[CDragListBox::Dragging](../Topic/CDragListBox::Dragging.md)|ドラッグ操作中にフレームワークによって呼び出されます。|  
|[CDragListBox::DrawInsert](../Topic/CDragListBox::DrawInsert.md)|ドラッグのリスト ボックスに挿入ガイドを描画します。|  
|[CDragListBox::Dropped](../Topic/CDragListBox::Dropped.md)|項目をドロップした後に、フレームワークによって呼び出されます。|  
|[CDragListBox::ItemFromPt](../Topic/CDragListBox::ItemFromPt.md)|ドラッグされた項目の座標を返します。|  
  
## 解説  
 この機能のリスト ボックスがどのような方法は、最も便利で、ユーザーはリストの項目を並べ替えることができます。  既定では、リスト ボックスはリストの項目を新しい場所に移動します。  ただし、それらを実行する代わりに項目をコピーするには `CDragListBox` のオブジェクトをカスタマイズできます。  
  
 `CDragListBox` のクラスに関連付けられているリスト ボックス コントロールは **LBS\_SORT** か **LBS\_MULTIPLESELECT** のスタイルを使用できません。  リスト ボックスのスタイルの詳細については、[リスト ボックス スタイル](../../mfc/reference/list-box-styles.md)を参照してください。  
  
 アプリケーションの既存のダイアログ ボックスにドラッグのリスト ボックスを使用するには、リスト ボックス コントロールをダイアログ テンプレートにダイアログ エディターを使用して追加し、次に、ダイアログ テンプレートのリスト ボックス コントロールに対応する \(カテゴリ `Control` と変数の型 `CDragListBox`\) のメンバー変数を割り当てます。  
  
 メンバー変数にコントロールを割り当てる方法の詳細については、[ダイアログ コントロールのメンバー変数を定義するに切り詰めて。](../../mfc/defining-member-variables-for-dialog-controls.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CListBox](../Topic/CListBox%20Class.md)  
  
 `CDragListBox`  
  
## 必要条件  
 **ヘッダー :** afxcmn.h  
  
## 参照  
 [MFC TSTCON サンプル](../../top/visual-cpp-samples.md)   
 [CListBox クラス](../Topic/CListBox%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CListBox クラス](../Topic/CListBox%20Class.md)