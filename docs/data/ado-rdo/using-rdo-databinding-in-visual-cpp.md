---
title: "Visual C++ で RDO データ バインドを使用する | Microsoft Docs"
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
  - "データ バインディング [C++], RDO"
  - "RDO [C++], データ バインド"
  - "RDO RemoteData コントロール, バインド (Visual C++ でデータを)"
  - "RemoteData コントロール, バインド (Visual C++ でデータを)"
ms.assetid: 02b9cfe7-7bbe-4a01-b075-e28d9536ac4b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++ で RDO データ バインドを使用する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ で RDO データ連結を使用するには、RDO RemoteData コントロールを追加し、データ ソースとレコード ソース \(SQL クエリ\) をポイントします。  また、RDO データ連結コントロールを追加し、RDO RemoteData コントロールをポイントし、RDO RemoteData コントロールのレコード ソースに連結するフィールドを選択します。  
  
### Visual C\+\+ で RDO データ連結を使用するには  
  
1.  [ODBC データ ソース](../../data/ado-rdo/odbc-connections.md)が設定されていない場合は、設定します。  
  
2.  MFC アプリケーション ウィザードで、MFC ダイアログ アプリケーションまたは MFC フォーム ビュー アプリケーションを作成します。  
  
3.  Microsoft RemoteData コントロール \(RDO RemoteData コントロール\) をダイアログ ボックスに追加します。「[Visual C\+\+ アプリケーションにコントロールを挿入する](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md)」を参照してください。  
  
4.  RDO RemoteData コントロールから ODBC データ ソースをポイントします。  
  
    1.  コントロールを右クリックし、**\[プロパティ\]** をクリックします。  
  
    2.  \[コントロール\] タブをクリックします。  
  
    3.  **DataSource** を ODBC データ ソースに設定します。  
  
    4.  必要に応じて、ODBC データ ソース用のユーザー名とパスワードを設定します。  データ ソースにユーザー名とパスワードが必要ない場合は、空白にしておきます。  
  
    5.  SQL クエリを \[SQL\] ボックスに入力します。  このクエリの結果にデータ連結コントロールを連結できます。  
  
5.  必要に応じて、RDO RemoteData コントロールのほかのプロパティを設定します。  
  
6.  データ連結コントロールを追加します。  ここでは、DBGrid コントロールを追加し、データ ソースを設定します。  
  
    1.  DBGrid を右クリックし、**\[プロパティ\]** をクリックします。  
  
    2.  **\[全ページ\]** タブをクリックします。  
  
    3.  **DataSource** プロパティで RDO RemoteData コントロールを指定します。  このプロパティのドロップダウン コンボ ボックスをクリックし、RDO RemoteData コントロールの ID を選択します。  既定の ID 名は、IDC\_REMOTEDATACTL1 です。  
  
7.  テスト モードで実行するには、Ctrl キーを押しながら T キーを押します。  データをスクロールできるようになります。  テスト モードを終了するには、**Esc** キーを押すか、ダイアログ ボックスを閉じます。  
  
 プログラムをコンパイルして実行すると、同じようにデータをスクロールできるようになります。  
  
## 参照  
 [RDO データ バインド](../../data/ado-rdo/rdo-databinding.md)   
 [Visual C\+\+ で ActiveX コントロールによるデータ連結を行う](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)