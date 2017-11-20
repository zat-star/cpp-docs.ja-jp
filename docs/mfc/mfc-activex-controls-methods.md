---
title: "MFC ActiveX コントロール: メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: MFC ActiveX controls [MFC], methods
ms.assetid: e20271de-6ffa-4ba0-848b-bafe6c9e510c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f1c0fe2f5e54205c3e9c82ebf1d9cb40504e5023
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-activex-controls-methods"></a>MFC ActiveX コントロール : メソッド
ActiveX コントロールは、それ自体とそのコントロールのコンテナー間の通信にイベントを発生させます。 コンテナーは、メソッドとプロパティを使用して、コントロールとも通信できます。 メソッドは、関数とも呼ばれます。  
  
 メソッドとプロパティは、オートメーション クライアントや ActiveX コントロール コンテナーなど、他のアプリケーションで使用するために、エクスポートされたインターフェイスを提供します。 ActiveX コントロールのプロパティの詳細については、記事を参照してください。 [MFC ActiveX コントロール: プロパティ](../mfc/mfc-activex-controls-properties.md)です。  
  
 メソッドは、C++ のクラスのメンバー関数を使用して、目的のと似ています。 コントロールを実装できるメソッドの 2 つの種類があります: 株価とカスタムです。 ストック イベント、メソッドの在庫のようなをこれらのメソッドは、 [COleControl](../mfc/reference/colecontrol-class.md)実装を提供します。 ストック メソッドの詳細については、記事を参照してください。 [MFC ActiveX コントロール: ストック メソッドの追加](../mfc/mfc-activex-controls-adding-stock-methods.md)です。 開発者は、によって定義されたカスタムのメソッドには、コントロールの他のカスタマイズができるようにします。 詳細については、記事を参照してください。 [MFC ActiveX コントロール: カスタム メソッドの追加](../mfc/mfc-activex-controls-adding-custom-methods.md)です。  
  
 Microsoft Foundation Class ライブラリ (MFC) は、株価、カスタム メソッドをサポートするために、コントロールをできる機構を実装します。 最初の部分はクラス`COleControl`です。 派生`CWnd`、`COleControl`メンバー関数は、すべての ActiveX コントロールに共通するストック メソッドをサポートします。 このメカニズムの 2 番目の部分は、ディスパッチ マップです。 ディスパッチ マップは、メッセージ マップに似ていますただし、関数を Windows メッセージの ID にマップするには、代わりにディスパッチ マップ仮想メンバー関数にマップ IDispatch ID。  
  
 さまざまなメソッドを正しくサポートするために、コントロールのクラスは、ディスパッチ マップを宣言する必要があります。 これを行うコントロール クラスのヘッダーにあるコードの次の行 (です。H) ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#13](../mfc/codesnippet/cpp/mfc-activex-controls-methods_1.h)]  
  
 ディスパッチ マップの主な目的は、(コンテナー) などの外部の呼び出し元とメソッドを実装するコントロールのクラスのメンバー関数で使用されるメソッド名の間のリレーションシップを確立するためにです。 ディスパッチ マップを宣言すると、コントロールの実装で定義されている必要があります (です。CPP) ファイルです。 次のコード行は、ディスパッチ マップを定義します。  
  
 [!code-cpp[NVC_MFC_AxUI#14](../mfc/codesnippet/cpp/mfc-activex-controls-methods_2.cpp)]  
[!code-cpp[NVC_MFC_AxUI#15](../mfc/codesnippet/cpp/mfc-activex-controls-methods_3.cpp)]  
  
 使用した場合、 [MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)プロジェクトを作成するには、これらの行が自動的に追加します。 MFC ActiveX コントロール ウィザードを使用しない場合は、これらの行を手動で追加する必要があります。  
  
 次の記事では、メソッドの詳細について説明します。  
  
-   [MFC ActiveX コントロール: ストック メソッドの追加](../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [MFC ActiveX コントロール: カスタム メソッドの追加](../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [MFC ActiveX コントロール: メソッドからのエラー コードのリターン](../mfc/mfc-activex-controls-returning-error-codes-from-a-method.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

