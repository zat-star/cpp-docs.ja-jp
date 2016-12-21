---
title: "チュートリアル: プロジェクトの構築 (C++) | Microsoft Docs"
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
  - "ビルド (プロジェクトを) [C++]"
  - "プロジェクト [C++]、ビルド"
  - "プロジェクトのビルド [C++]"
ms.assetid: d459bc03-88ef-48d0-9f9a-82d17f0b6a4d
caps.latest.revision: 14
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# チュートリアル: プロジェクトの構築 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このチュートリアルでは、コードに意図的に Visual C\+\+ 構文のエラーを挿入し、コンパイル エラーがどのように表示されるかを確認し、その修正方法について説明します。  プロジェクトをコンパイルすると、エラー メッセージによって問題の内容と発生した場所が示されます。  
  
## 必須コンポーネント  
  
-   このチュートリアルは、C\+\+ 言語の基本を理解していることを前提としています。  
  
-   また、これまでの関連チュートリアル \(「[C\+\+ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照\) を完了していることも必要です。  
  
### コンパイル エラーを修正するには  
  
1.  TestGames.cpp で、次のように最後の行のセミコロンを削除します。  
  
     `return 0`  
  
2.  メニュー バーの **\[ビルド\]**、**\[ソリューションのビルド\]** の順にクリックします。  
  
3.  **\[エラー リスト\]** ウィンドウに、プロジェクトのビルド中にエラーが発生したことを示すメッセージが表示されます。  たとえば、エラーの説明は次のようになります。  
  
     `error C2143: syntax error : missing ';' before '}'`  
  
     このエラーに関するヘルプ情報を表示するには、**\[エラー リスト\]** ウィンドウでそのエラーを強調表示し、F1 キーを押します。  
  
4.  構文エラーのある行の最後に、セミコロンを戻します。  
  
     `return 0;`  
  
5.  メニュー バーの **\[ビルド\]**、**\[ソリューションのビルド\]** の順にクリックします。  
  
     **\[出力\]** ウィンドウに、プロジェクトが正常にコンパイルされたことを示すメッセージが表示されます。  
  
  **1\>\-\-\-\-\-\- Build started: Project: Game, Configuration: Debug Win32 \-\-\-\-\-\-**  
**1\>  TestGames.cpp**  
**1\>  Game.vcxproj \-\> C:\\Users\\\<username\>\\Documents\\Visual Studio *\<version\>*\\Projects\\Game\\Debug\\Game.exe**  
**\=\=\=\=\=\=\=\=\=\= Build: 1 succeeded, 0 failed, 0 up\-to\-date, 0 skipped \=\=\=\=\=\=\=\=\=\=**  
  
## 次の手順  
 **前へ :** [チュートリアル: プロジェクトとソリューションの使用 \(C\+\+\)](../Topic/Walkthrough:%20Working%20with%20Projects%20and%20Solutions%20\(C++\).md) &#124; **次へ :** [チュートリアル: プロジェクトのテスト \(C\+\+\)](../ide/walkthrough-testing-a-project-cpp.md)  
  
## 参照  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ja-jp/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [DELETE\_PENDING\_Building and Debugging](http://msdn.microsoft.com/ja-jp/9f6ba537-5ea0-46fb-b6ba-b63d657d84f1)