---
title: "MFC ActiveX コントロール : メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC ActiveX コントロール, メソッド"
ms.assetid: e20271de-6ffa-4ba0-848b-bafe6c9e510c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC ActiveX コントロール : メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ActiveX コントロールは、それ自身とコントロール コンテナーの間で通信するためにイベントを発生させます。  コンテナーは、メソッドやプロパティによってコントロールと通信できます。  メソッドまたは関数といいます。  
  
 メソッドとプロパティは、オートメーション クライアントと ActiveX コントロール コンテナーなどの他のアプリケーションでの使用にエクスポートされたインターフェイスを提供します。  ActiveX コントロール プロパティ詳細については、記事 [MFC ActiveX コントロール: プロパティ](../mfc/mfc-activex-controls-properties.md)を参照します。  
  
 メソッドは、.クラスのメンバー関数に似た使用中と適切です。  コントロールを実装するメソッドの 2 種類があります。: ストック イベントとカスタム。  ストック イベント、ストック メソッドに似ていますが [COleControl](../mfc/reference/colecontrol-class.md) 実装を提供するこれらのメソッドです。  ストック メソッドの詳細については、記事 [MFC ActiveX コントロール: ストック メソッドの追加](../mfc/mfc-activex-controls-adding-stock-methods.md)を参照します。  開発者が定義するカスタム メソッドはコントロールのカスタマイズができます。  詳細については、記事 [MFC ActiveX コントロール: カスタム メソッドの追加](../mfc/mfc-activex-controls-adding-custom-methods.md)を参照します。  
  
 Microsoft Foundation Class ライブラリ \(MFC\) は、コントロールがストック イベントとカスタム メソッドをサポートできるようにする機能を実装します。  最初の部分は、クラス `COleControl`です。  `CWnd`から派生されて、`COleControl` のメンバー関数は、すべての ActiveX コントロールに共通のストック メソッドをサポートします。  この機能の 2 番目の部分は、ディスパッチ マップです。  ディスパッチ マップでは、メッセージ マップに似ています; ただし、Windows メッセージ ID への関数を割り当てる代わりに、ディスパッチ マップは、IDispatch IDS に仮想メンバー関数を割り当てます。  
  
 さまざまなメソッドを正しくサポートするコントロール クラスはディスパッチ マップを宣言する必要があります。  これは、コントロール クラスのヘッダーに、次のコード行によって実現されます。H\) ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#13](../mfc/codesnippet/CPP/mfc-activex-controls-methods_1.h)]  
  
 ディスパッチ マップの主な目的は、外部の呼び出し元が使用するメソッド名 \(コンテナーなど\) にメソッドを実装するコントロール クラスのメンバー関数との関係を確立します。  ディスパッチ マップを宣言した後、コントロールの実装 \(.cpp\) ファイルで定義されている必要があります。  次のコードは、ディスパッチ マップを定義する:  
  
 [!code-cpp[NVC_MFC_AxUI#14](../mfc/codesnippet/CPP/mfc-activex-controls-methods_2.cpp)]  
[!code-cpp[NVC_MFC_AxUI#15](../mfc/codesnippet/CPP/mfc-activex-controls-methods_3.cpp)]  
  
 プロジェクトの作成に [MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md) を使用してこれらの行が自動的に追加されます。  MFC ActiveX コントロール ウィザードを使用しないと、次の行を手動で追加する必要があります。  
  
 次のトピックでは、メソッドを解説します:  
  
-   [MFC ActiveX コントロール: ストック メソッドの追加](../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [MFC ActiveX コントロール: カスタム メソッドの追加](../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [MFC ActiveX コントロール: メソッドから返されるエラー コード](../mfc/mfc-activex-controls-returning-error-codes-from-a-method.md)  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)