---
title: "CWaitCursor クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWaitCursor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "カーソル, 待機カーソル"
  - "CWaitCursor クラス"
  - "待機カーソル"
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWaitCursor クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

時間がかかる処理を実行している最中に、通常は砂時計として表示される待機カーソルを表示する 1 つの方法を提供します。  
  
## 構文  
  
```  
class CWaitCursor  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CWaitCursor::CWaitCursor](../Topic/CWaitCursor::CWaitCursor.md)|`CWaitCursor` オブジェクトを構築し、待機カーソルを表示します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CWaitCursor::Restore](../Topic/CWaitCursor::Restore.md)|変更された後に待機カーソルを復元します。|  
  
## 解説  
 `CWaitCursor` には、基本クラスはありません。  
  
 正確な Windows プログラミングでは、時間がかかる処理を実行するときに、常に待機カーソルを表示する必要があります。  
  
 待機カーソルを表示するには、時間がかかる処理のコードの前に `CWaitCursor` 変数を定義するだけです。  オブジェクトのコンストラクターが、自動的に待機カーソルを表示するようにします。  
  
 オブジェクトがスコープ外 \(`CWaitCursor` オブジェクトが宣言されたブロックの終わり\) になると、デストラクターは、カーソルを以前のカーソルに戻します。  つまり、オブジェクトは必要な後処理を自動的に行います。  
  
> [!NOTE]
>  コンストラクターとデストラクターの動作方法のため、`CWaitCursor` オブジェクトは、常にローカル変数として宣言します。グローバル変数として宣言したり、**new** を使って割り当てないでください。  
  
 メッセージ ボックスやダイアログ ボックスを表示するなどのカーソルが変更される操作を実行するときは、待機カーソルを元に戻すために、[Restore](../Topic/CWaitCursor::Restore.md) メンバー関数を呼び出します。  待機カーャ汲ｪ侮ｦされているときでも、Restore を呼び出すことができます。  
  
 待機カーソルを表示するもう 1 つの方法として、[CCmdTarget::BeginWaitCursor](../Topic/CCmdTarget::BeginWaitCursor.md)、[CCmdTarget::EndWaitCursor](../Topic/CCmdTarget::EndWaitCursor.md)、[CCmdTarget::RestoreWaitCursor](../Topic/CCmdTarget::RestoreWaitCursor.md) を組み合わせて使う方法があります。  しかし、時間がかかる処理が終わったときにカーソルを前のカーソルに戻す必要はないので、`CWaitCursor` の方がより使いやすくなっています。  
  
> [!NOTE]
>  MFC は、[CWinApp::DoWaitCursor](../Topic/CWinApp::DoWaitCursor.md) を使用してカーソルを設定、および復元します。  独自の動作を提供するために、この関数をオーバライドできます。  
  
## 継承階層  
 `CWaitCursor`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 使用例  
 [!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/CPP/cwaitcursor-class_1.cpp)]  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCmdTarget::BeginWaitCursor](../Topic/CCmdTarget::BeginWaitCursor.md)   
 [CCmdTarget::EndWaitCursor](../Topic/CCmdTarget::EndWaitCursor.md)   
 [CCmdTarget::RestoreWaitCursor](../Topic/CCmdTarget::RestoreWaitCursor.md)   
 [CWinApp::DoWaitCursor](../Topic/CWinApp::DoWaitCursor.md)   
 [操作方法: Microsoft Foundation Class アプリケーションのマウス カーソルを変更します。](http://go.microsoft.com/fwlink/?LinkID=128044)