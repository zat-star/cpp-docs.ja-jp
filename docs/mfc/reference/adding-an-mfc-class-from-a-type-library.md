---
title: "タイプ ライブラリからの MFC クラスの追加 | Microsoft Docs"
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
  - "クラス [C++], 追加 (MFC を)"
  - "MFC, 追加 (クラスをタイプ ライブラリから)"
  - "タイプ ライブラリ, 追加 (MFC クラスを)"
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# タイプ ライブラリからの MFC クラスの追加
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このウィザードを使用して、利用できるタイプ ライブラリのインターフェイスから MFC クラスを作成します。  MFC クラスは、[MFC アプリケーション](../../mfc/reference/creating-an-mfc-application.md)、[MFC DLL](../../mfc/reference/creating-an-mfc-dll-project.md)、および [MFC ActiveX コントロール](../../mfc/reference/creating-an-mfc-activex-control.md)に追加できます。  
  
> [!NOTE]
>  タイプ ライブラリからクラスを追加するために、オートメーションを有効にして MFC プロジェクトを作成する必要はありません。  
  
 タイプ ライブラリには、コンポーネントによって公開されたインターフェイスのバイナリ記述が含まれます。この記述では、メソッド、およびそのパラメーターと戻り値の型が定義されます。  Typelib クラス追加ウィザードの \[使用できるタイプ ライブラリ\] ボックスの一覧にタイプ ライブラリを表示するには、タイプ ライブラリを登録する必要があります。  詳細については、MSDN ライブラリの「Inside Distributed COM: Type Libraries and Language Integration」を参照してください。  
  
### タイプ ライブラリから MFC クラスを追加するには  
  
1.  **ソリューション エクスプローラー**または[クラス ビュー](http://msdn.microsoft.com/ja-jp/8d7430a9-3e33-454c-a9e1-a85e3d2db925)で、クラスを追加するプロジェクトの名前を右クリックします。  
  
2.  ショートカット メニューの \[追加\] をポイントし、\[クラスの追加\] をクリックします。  
  
3.  [&#91;クラスの追加&#93;](../../ide/add-class-dialog-box.md) ダイアログ ボックスのテンプレート ペインの \[TypeLib からの MFC クラス\] をクリックし、次に \[開く\] をクリックして[Typelib クラス追加ウィザード](../../mfc/reference/add-class-from-typelib-wizard.md)を表示します。  
  
 このウィザードでは、タイプ ライブラリ内の複数のクラスを追加できます。  同様に、1 回のウィザード セッションで複数のタイプ ライブラリからクラスを追加できます。  
  
 このウィザードによって、選択したタイプ ライブラリから追加するインターフェイスごとに、[COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md) から派生した MFC クラスが作成されます。  `COleDispatchDriver` によって OLE オートメーションのクライアント側が実装されます。  
  
## 参照  
 [オートメーション クライアント](../../mfc/automation-clients.md)   
 [オートメーション クライアント : タイプ ライブラリの使用](../Topic/Automation%20Clients:%20Using%20Type%20Libraries.md)