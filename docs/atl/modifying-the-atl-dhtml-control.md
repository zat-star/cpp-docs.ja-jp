---
title: "ATL DHTML コントロールの変更 | Microsoft Docs"
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
  - "DHTML コントロール"
  - "DHTML コントロール, 変更"
  - "HTML コントロール, 変更"
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ATL DHTML コントロールの変更
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL コントロール ウィザードは初期コードを備えています。コントロールをビルドして実行できます。つまり、メソッドがプロジェクト ファイルに書き込む方法と、ディスパッチまたはメソッドを使用して、コントロールの C\+\+ コードへの呼び出しに DHTML 確認できます。  ディスパッチ インターフェイスにメソッドを追加できます。  次に、HTML リソースのメソッドを呼び出します。  
  
#### ATL DHTML コントロールを変更するには  
  
1.  クラス ビューで、コントロール プロジェクトを配置します。  
  
     に「UI に」持つ `OnClick`を 1 とおりの方法でインターフェイス注意してください。  UI 「」で終わるインターフェイスには、メソッドはありません。  
  
2.  `MethodInvoked`と呼ばれる「UI 内で」終了インターフェイスにメソッドを追加します。  
  
     このメソッドはコンテナーの対話にコントロール コンテナーで使用されるコントロールと対話するために DHTML で使用しているインターフェイスへのインターフェイスではなくに追加されます。  コンテナーだけこのメソッドを呼び出すことができます。  
  
3.  .cpp ファイルのスタブ メソッドを検索し、メッセージ ボックスを表示するコードを追加します \(例:  
  
     [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/CPP/modifying-the-atl-dhtml-control_1.cpp)]  
  
4.  今度はだけで「UI 内で」終了、インターフェイスに追加します `HelloHTML`と呼ばれる別のメソッドを追加します。.cpp ファイルの `HelloHTML` のスタブ メソッドを検索し、メッセージ ボックスを表示するコードを追加します \(例:  
  
     [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/CPP/modifying-the-atl-dhtml-control_2.cpp)]  
  
5.  「UI 内で」終了インターフェイスに 3 番目のメソッド、`GoToURL`を追加します。[IWebBrowser2::Navigate](https://msdn.microsoft.com/en-us/library/aa752133.aspx)を呼び出してこのメソッドを実装して、次のように、:  
  
     [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/CPP/modifying-the-atl-dhtml-control_3.cpp)]  
  
     ATL は、の .h ファイルでそのインターフェイスへのポインターを提供するため **IWebBrowser2** のメソッドを使用できます。  
  
 次に、作成したメソッドを呼び出すに HTML リソースを変更します。  これらのメソッドを呼び出すには、次の 3 種類のボタンを追加します。  
  
#### HTML リソースを変更するには  
  
1.  ソリューション エクスプローラーで、HTML リソースを表示するには、.htm ファイルをダブルクリックします。  
  
     HTML、外部 Windows のディスパッチ特にメソッドへの呼び出しを確認します。  HTML は、プロジェクトの `OnClick` のメソッドを呼び出し、パラメーターは割り当て \("`red`"\) にコントロール \(`theBody`\) および色の本体を示します。  メソッドの呼び出し後のテキストは、ボタンに表示されるラベルです。  
  
2.  `OnClick` の別のメソッドを変更、色追加します。  以下はその例です。  
  
    ```  
    <br>  
    <br>  
    <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>  
    ```  
  
     このメソッドは、元、白い背景にコントロールを返すため、ユーザーがクリックできる **\[最新の情報に更新\]**というラベルのボタンを作成します。  
  
3.  作成した `HelloHTML` のメソッドの呼び出しを追加します。  以下はその例です。  
  
    ```  
    <br>  
    <br>  
    <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>  
    ```  
  
     このメソッドは `HelloHTML` のメッセージ ボックスを表示するユーザーがクリックできる **HelloHTML**というラベルのボタンを作成します。  
  
 [変更された DHTML コントロールをテストします。](../atl/testing-the-modified-atl-dhtml-control.md)ビルドするようになりました。  
  
## 参照  
 [DHTML コントロールのサポート](../atl/atl-support-for-dhtml-controls.md)