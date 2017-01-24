---
title: "MFC ActiveX コントロール : オートメーション サーバーの作成 | Microsoft Docs"
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
  - "ActiveX コントロール [C++], オートメーション サーバー"
  - "オートメーション サーバー [C++], MFC ActiveX コントロール"
  - "MFC ActiveX コントロール [C++], オートメーション サーバー"
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX コントロール : オートメーション サーバーの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オートメーション サーバーとしてプログラムに別のアプリケーションでそのコントロールおよびアプリケーションのコントロールでのメソッド呼び出しを埋め込むために MFC ActiveX コントロールを開発できます。  このようなコントロールは、ActiveX コントロール コンテナーでホストされている使用できます。  
  
### コントロールをオートメーション サーバーとして作成するには  
  
1.  [作成](../mfc/reference/mfc-activex-control-wizard.md) コントロール。  
  
2.  [メソッドを追加します](../mfc/mfc-activex-controls-methods.md)。  
  
3.  オーバーライド [IsInvokeAllowed](../Topic/COleControl::IsInvokeAllowed.md)。  詳細については、サポート技術情報の文書 Q146120 を参照します。  
  
4.  コントロールをビルドします。  
  
### プログラムでオートメーション サーバーのメソッドにアクセスするには  
  
1.  たとえば、アプリケーション [MFC の exe](../Topic/MFC%20Application%20Wizard.md)を作成します。  
  
2.  `InitInstance` 関数の先頭に次の行を追加する:  
  
     [!code-cpp[NVC_MFC_AxCont#17](../mfc/codesnippet/CPP/mfc-activex-controls-creating-an-automation-server_1.cpp)]  
  
3.  クラス ビューで、プロジェクト ノードを右クリックし、タイプ ライブラリをインポートするに **Typelib クラス追加ウィザード** を選択します。  
  
     これはプロジェクトにファイル名拡張子の .h ファイルと .cpp ファイルを追加します。  
  
4.  ActiveX コントロールの一つ以上のメソッドを呼び出すクラスのヘッダー ファイルで次の行を追加する: ファイル名がタイプ ライブラリをインポートするときに作成されるヘッダー ファイルの名前です。`#include filename.h`。  
  
5.  呼び出しが ActiveX コントロールのメソッドに対して関数では、コントロールのラッパー クラスのオブジェクトを作成して追加し、ActiveX オブジェクトを作成するコードを示します。  たとえば、次の MFC コードは、OK ボタンがダイアログ ボックス内でクリックすると `CCirc` のコントロールをインスタンス化し、Caption プロパティを取得し、結果を表示する:  
  
     [!code-cpp[NVC_MFC_AxCont#18](../mfc/codesnippet/CPP/mfc-activex-controls-creating-an-automation-server_2.cpp)]  
  
 アプリケーションで使用すると ActiveX コントロールにメソッドを追加する場合は、タイプ ライブラリをインポートするときに作成されたファイルを削除して、アプリケーションでコントロールの最新バージョンを使用できます。  その後、タイプ ライブラリを再度インポートします。  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)