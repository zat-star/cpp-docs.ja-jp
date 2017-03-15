---
title: "OLE コントロール クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX クラス [C++]"
  - "ActiveX コントロール クラス [C++]"
  - "ActiveX コントロール [C++], OLE コントロール クラス"
  - "カスタム コントロール [MFC], クラス"
  - "OLE コントロール クラス [C++]"
  - "OLE コントロール [C++], クラス"
  - "再利用できるコンポーネント クラス"
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE コントロール クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのロールは、使用する基本クラスです OLE コントロールを作成する場合。  OLE コントロール モジュールの `COleControlModule` クラスは、アプリケーションの [CWinApp](../mfc/reference/cwinapp-class.md) クラスに似ています。  各モジュールが、一つ以上の OLE コントロールを実装します; これらのコントロールは `COleControl` オブジェクトによって表されます。  これらのコントロールは `CConnectionPoint` オブジェクトを使用してコンテナーと通信します。  
  
 `CPictureHolder` と `CFontHolder` クラスは `COlePropertyPage` と `CPropExchange` クラスは、コントロール用のプロパティ ページとプロパティの永続性を実装するのに役立ちますが、画像やフォントの COM インターフェイスをカプセル化します。  
  
 [COleControlModule](../mfc/reference/colecontrolmodule-class.md)  
 OLE コントロール モジュールの `CWinApp` クラスを置き換えます。  OLE コントロール モジュール オブジェクトを開発するに `COleControlModule` クラスから派生してください。  これは OLE コントロール モジュールを初期化するためのメンバー関数を提供します。  
  
 [COleControl](../mfc/reference/colecontrol-class.md)  
 OLE コントロールを作成するに `COleControl` クラスから派生してください。  `CWnd`から派生されて、このクラスはイベントの発生と機能などの追加 OLE 固有の機能とウィンドウ オブジェクトのすべての機能を、メソッドとプロパティをサポートする継承します。  
  
 [CConnectionPoint](../Topic/CConnectionPoint%20Class.md)  
 `CConnectionPoint` クラスは他の OLE オブジェクトとの通信に使用されるコネクション ポイントと呼ばれる特別な型のインターフェイスを定義します。  コネクション ポイント イベントが発生すると変更通知などの他のオブジェクトの操作、開始アウトゴーイング インターフェイスを実装します。  
  
 [CPictureHolder](../mfc/reference/cpictureholder-class.md)  
 Windows の画像オブジェクトと `IPicture` COM インターフェイスの機能をカプセル化した; OLE コントロールのカスタム ピクチャ プロパティを実装するために使用します。  
  
 [CFontHolder](../mfc/reference/cfontholder-class.md)  
 Windows のフォント オブジェクトと `IFont` COM インターフェイスの機能をカプセル化した; OLE コントロールのストック フォント プロパティを実装するために使用します。  
  
 [COlePropertyPage クラス](../mfc/reference/colepropertypage-class.md)  
 ダイアログ ボックスのようなグラフィカル インターフェイスの OLE コントロールのプロパティが表示されます。  
  
 [CPropExchange](../Topic/CPropExchange%20Class.md)  
 OLE コントロールのプロパティの永続性の実装をサポートします。  ダイアログ ボックスの [CDataExchange](../Topic/CDataExchange%20Class.md) と似ています。  
  
 [CMonikerFile](../Topic/CMonikerFile%20Class.md)  
 モニカーを名前であるストリームにモニカーを、モニカーにすることができ、バインド同期的にオブジェクトの文字列形式。  
  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)  
 同様に、作業 `CMonikerFile`に; ただし、モニカーを名前であるストリームに非同期的にモニカーをバインドします。  
  
 [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)  
 非同期で読み込める OLE コントロール プロパティを実装します。  
  
 [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)  
 非同期で転送し、メモリ ファイルにキャッシュする OLE コントロール プロパティを実装します。  
  
 [COleCmdUI](../mfc/reference/colecmdui-class.md)  
 アクティブ文書をコンテナーをアクティブ ドキュメントのユーザー インターフェイスで作成されたコマンドを受け取るコマンド コンテナーのユーザー インターフェイスに \(FileNew の、印刷などのなど\) を発生、割り当てを受け取るようにします。  
  
 [COleSafeArray](../mfc/reference/colesafearray-class.md)  
 任意の型および次元の配列を使用します。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)