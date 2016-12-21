---
title: "チュートリアル: プロジェクトのデバッグ (C++) | Microsoft Docs"
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
  - "デバッグ (プロジェクトを)"
  - "プロジェクトのデバッグ [C++]"
  - "プロジェクト [C++], デバッグ"
ms.assetid: a5cade77-ba51-4b03-a7a0-6897e3cd6a59
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# チュートリアル: プロジェクトのデバッグ (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このチュートリアルでは、プロジェクトのテスト時に検出された問題を修正するため、プログラムに変更を加えます。  
  
## 必須コンポーネント  
  
-   このチュートリアルは、C\+\+ 言語の基本を理解していることを前提としています。  
  
-   また、これまでの関連チュートリアル \(「[C\+\+ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照\) を完了していることも必要です。  
  
### バグがあるプログラムを修正するには  
  
1.  `Cardgame` オブジェクトが破棄されるとどうなるかを確認するには、`Cardgame` クラスのデストラクターを見ます。  
  
     メニュー バーで **\[表示\]**、**\[クラス ビュー\]** の順にクリックします。  
  
     **\[クラス ビュー\]** ウィンドウで、**\[Game\]** プロジェクト ツリーを展開し、**\[Cardgame\]** クラスを選択して、クラス メンバーとメソッドを表示します。  
  
     **~Cardgame\(void\)** デストラクターのショートカット メニューを開き、**\[定義へ移動\]** を選択します。  
  
2.  Cardgame が終了したときに `totalParticipants` を減らすには、`Cardgame::~Cardgame` デストラクターの左右の中かっこの間に次のコードを入力します。  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]  
  
3.  変更後、Cardgame.cpp ファイルは次のようになります。  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]  
  
4.  メニュー バーの **\[ビルド\]**、**\[ソリューションのビルド\]** の順にクリックします。  
  
5.  ビルドが完了したら、メニュー バーの **\[デバッグ\]**、**\[デバッグ開始\]** を選択するか、または F5 キーを選択してデバッグ モードで実行します。  プログラムは、最初のブレークポイントで停止します。  
  
6.  プログラムを実行するには、メニュー バーで **\[デバッグ\]**、**\[ステップ オーバー\]** の順に選択するか、F10 キーを押します。  
  
     Cardgame コンストラクターが実行されるたびに `totalParticipants` の値が増加します。  `PlayGames` 関数が返されると、Cardgame インスタンスがスコープ外に出て削除される \(デストラクターが呼び出される\) ため、`totalParticipants` が減少します。  `return` ステートメントが実行される直前に、`totalParticipants` は 0 になります。  
  
7.  プログラムが終了するまで続行するか、またはメニュー バーの **\[デバッグ\]**、**\[実行\]** を選択するか F5 キーを選択して続行します。  
  
## 次の手順  
 **前へ :** [チュートリアル: プロジェクトのテスト \(C\+\+\)](../ide/walkthrough-testing-a-project-cpp.md) &#124; **次へ :** [チュートリアル: プログラムの配置 \(C\+\+\)](../ide/walkthrough-deploying-your-program-cpp.md)  
  
## 参照  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ja-jp/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [DELETE\_PENDING\_Building and Debugging](http://msdn.microsoft.com/ja-jp/9f6ba537-5ea0-46fb-b6ba-b63d657d84f1)