---
title: "Creating a New Custom or Data Resource | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.binary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "custom resources [C++]"
  - "data resources [C++]"
  - "resources [Visual Studio], creating"
ms.assetid: 9918bf96-38fa-43a1-a384-572f95d84950
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Creating a New Custom or Data Resource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

通常のリソース スクリプト \(.rc\) ファイル構文を使用してリソースを別個のファイルに置き、それからソリューション エクスプローラーでプロジェクトを右クリックして、ショートカット メニューで **\[リソース ファイルのインクルード\]** をクリックしてそのファイルをインクルードすることにより、新しいカスタム リソースやデータ リソースを作成することができます。  
  
### 新しいカスタム リソースやデータ リソースを作成するには  
  
1.  カスタム リソースやデータ リソースが格納される [.rc ファイルを作成します](../windows/how-to-create-a-resource-script-file.md)。  
  
     null で終わる引用符で囲まれた文字列として、または 10 進数、16 進数、または 8 進数形式の整数として.rc ファイルにカスタム データを入力することができます。  
  
2.  **ソリューション エクスプローラー**でプロジェクトの .rc ファイルを右クリックし、ショートカット メニューの **\[リソース ファイルのインクルード\]** をクリックします。  
  
3.  **\[コンパイル時に追加するファイル\]** ボックスで、カスタム リソースが格納されるファイルの名前を指定する **\#include** ステートメントを入力します。 例:  
  
    ```  
    #include mydata.rc  
    ```  
  
     入力する構文とスペルが正しいことを確認します。**\[コンパイル時に追加するファイル\]** ボックスの内容が、入力したとおりにリソース スクリプト ファイルに挿入されます。  
  
4.  **\[OK\]** をクリックして変更を記録します。  
  
 カスタム リソースを作成する別の方法として、外部ファイルをカスタム リソースとしてインポートする方法もあります。 詳細については、「[リソースのインポートとエクスポート](../windows/how-to-import-and-export-resources.md)」を参照してください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」をご覧ください。  
  
 要件  
  
 Win32  
  
## 参照  
 [Binary Editor](../mfc/binary-editor.md)