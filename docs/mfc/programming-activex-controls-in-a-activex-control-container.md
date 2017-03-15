---
title: "ActiveX コントロール コンテナー : ActiveX コントロール コンテナーでの ActiveX コントロールのプログラミング | Microsoft Docs"
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
  - "ActiveX コントロール コンテナー [C++], アクセス (ActiveX コントロールに)"
  - "ActiveX コントロール コンテナー [C++], ラッパー クラス"
  - "ActiveX コントロール [C++], アクセス"
  - "ActiveX コントロール [C++], ラッパー クラス"
  - "確認ダイアログ ボックス (生成されたクラスを)"
  - "ヘッダー ファイル [C++], ActiveX コントロール ラッパー クラスの"
  - "MFC ActiveX コントロール [C++], アクセス (コンテナーで)"
  - "ラッパー クラス [C++], ActiveX コントロール"
  - "ラッパー クラス [C++], 使用"
ms.assetid: ef9b2480-92d6-4191-b16e-8055c4fd7b73
caps.latest.revision: 8
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX コントロール コンテナー : ActiveX コントロール コンテナーでの ActiveX コントロールのプログラミング
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、埋め込まれたな ActiveX コントロールの公開 [メソッド](../mfc/mfc-activex-controls-methods.md) と [プロパティ](../mfc/mfc-activex-controls-properties.md) にアクセスするためのプロセスについて説明します。  基本的には、次の手順に従います。:  
  
1.  ギャラリー を使用して[ActiveX コンテナーのプロジェクトに ActiveX コントロールを挿入します。](../mfc/inserting-a-control-into-a-control-container-application.md)。  
  
2.  [メンバー変数を定義します。](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) \(または同じのアクセスの他のフォーム\) ActiveX コントロールのラッパー クラスとして入力します。  
  
3.  ラッパー クラスの定義済みのなメンバー関数を使用して[ActiveX コントロールをプログラミングします。](#_core_programming_the_activex_control)。  
  
 ここでは、ActiveX コントロール サポートとダイアログ ベースのプロジェクト \(名前付きな Container\) を作成したとします。  Circ サンプル コントロール、Circ は、プロジェクトに追加されます。  
  
 Circ のコントロールがプロジェクトに挿入されます \(手順 1\) はアプリケーションのメイン ダイアログ ボックスに、Circ のコントロールのインスタンスを挿入します。  
  
## 手順  
  
#### Circ のダイアログ コントロールをテンプレートに追加するには  
  
1.  ActiveX コントロール コンテナーのプロジェクトを読み込んでください。  この例では、`Container` のプロジェクトを使用します。  
  
2.  \[リソース ビュー\] タブをクリックします。  
  
3.  **ダイアログ** フォルダーを開きます。  
  
4.  メイン ダイアログ ボックスのテンプレートをダブルクリックします。  この例では、**IDD\_CONTAINER\_DIALOG**を使用します。  
  
5.  ツールボックスで、Circ のコントロール アイコンをクリックします。  
  
6.  Circ のコントロールを挿入できるように、ダイアログ ボックス内の場所をクリックします。  
  
7.  **ファイル** メニューのダイアログ ボックス テンプレートへのすべての変更を保存するに **すべて保存** を選択します。  
  
## プロジェクトの変更  
 Circ のコントロールにアクセスするコンテナー アプリケーションを有効にするには、Visual C\+\+ はコンテナーのプロジェクトおよびラッパー クラスのヘッダーに自動的にラッパー クラス \(`CCirc`\) の実装ファイル \(.cpp\) を追加します。H\) ダイアログ ボックスのヘッダー ファイルにファイル:  
  
 [!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/CPP/programming-activex-controls-in-a-activex-control-container_1.h)]  
  
##  <a name="_core_the_wrapper_class_header_28h29_file"></a> ラッパー クラスのヘッダー \(。H\) ファイル  
 取得するには、Circ のコントロールのプロパティ \(メソッドを呼び出す場合など\)、`CCirc` ラッパー クラス公開されているすべてのメソッドおよびプロパティの宣言を指定します。  例では、これらの宣言は CIRC.H.にあります。  次の例では、ActiveX コントロールの公開されたインターフェイスを定義するクラス `CCirc` 部分です:  
  
 [!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/CPP/programming-activex-controls-in-a-activex-control-container_2.h)]  
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/CPP/programming-activex-controls-in-a-activex-control-container_3.h)]  
  
 これらの関数は、通常の C\+\+ 構文を使用すると、アプリケーションの他のプロシージャからして呼び出すことができます。  コントロールのメソッドおよびプロパティにアクセスするためにこのメンバー関数を使用する詳細についてはセクション [ActiveX コントロールのプログラミング](#_core_programming_the_activex_control)を参照します。  
  
##  <a name="_core_member_variable_modifications_to_the_project"></a> プロジェクトへのメンバー変数の変更  
 ActiveX コントロールがプロジェクトに追加され、ダイアログ ボックスのコンテナーに埋め込まれている場合は、プロジェクトの他の部分にアクセスできます。  コントロールにアクセスする最も簡単な方法は、ダイアログ クラスの [メンバー変数を作成します。](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)、`CContainerDlg` \(Visual C\+\+ によってプロジェクトに追加するラッパー クラスの型と同じ手順 2 に含まれています。  その後、埋め込みコントロールにいつでもアクセスにメンバー変数を使用できます。  
  
 **メンバー変数の追加** ダイアログ ボックスは、プロジェクトに `m_circctl` のメンバー変数を追加する場合は、ヘッダー ファイルに次の行を追加します。`CContainerDlg` クラスの H\) :  
  
 [!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/CPP/programming-activex-controls-in-a-activex-control-container_4.h)]  
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/CPP/programming-activex-controls-in-a-activex-control-container_5.h)]  
  
 また、**DDX\_Control** の呼び出しは `DoDataExchange`の `CContainerDlg` の実装に自動的に追加します:  
  
 [!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/CPP/programming-activex-controls-in-a-activex-control-container_6.cpp)]  
  
##  <a name="_core_programming_the_activex_control"></a> ActiveX コントロールのプログラミング  
 この時点で、ダイアログ テンプレートに ActiveX コントロールを挿入し、このコントロールのメンバー変数を作成します。  、組み込みコントロールのプロパティとメソッドにアクセスするには、共通 C\+\+ 構文を使用できます。  
  
 注意として \([ラッパー クラスのヘッダー \(。H\) ファイル](#_core_the_wrapper_class_header_28h29_file)\) で、ヘッダー ファイル \(。`CCirc` のラッパー クラスの H\)、この場合 CIRC.H は、公開されたプロパティ値を取得および設定するために使用できるメンバー関数の一覧が表示されます。  公開されたメソッドのメンバー関数も使用できます。  
  
 コントロールのプロパティを変更する共通の場所はメイン ダイアログ クラスの `OnInitDialog` のメンバー関数です。  この関数は、コントロールのいずれかがダイアログ ボックスが表示され、内容を初期化するために使用される直前に呼び出されます。  
  
 次のコード例は Circ の埋め込まれたなコントロールのキャプションと CircleShape のプロパティを変更するに `m_circctl` のメンバー変数を使用して:  
  
 [!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/CPP/programming-activex-controls-in-a-activex-control-container_7.cpp)]  
  
## 参照  
 [ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)