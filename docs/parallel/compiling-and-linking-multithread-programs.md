---
title: "マルチスレッド プログラムのコンパイルとリンク | Microsoft Docs"
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
  - "コンパイル (マルチスレッド プログラムを)"
  - "コンパイル (ソース コードを) [C++], マルチスレッド プログラム"
  - "リンク [C++], マルチスレッド プログラム"
  - "マルチスレッド処理 [C++], コンパイル済みプログラム"
  - "マルチスレッド処理 [C++], リンク (プログラムを)"
  - "スレッド処理 [C++], コンパイル済みプログラム"
  - "スレッド処理 [C++], リンク (プログラムを)"
ms.assetid: 27589afc-daf2-4f26-b868-a99de5c9dfec
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# マルチスレッド プログラムのコンパイルとリンク
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bounce.c プログラムについては、「[マルチスレッドの C サンプル プログラム](../parallel/sample-multithread-c-program.md)」で説明しています。  
  
 既定では、プログラムはマルチスレッドにコンパイルされます。  
  
#### Bounce.c マルチスレッド プログラムを開発環境内でコンパイルおよびリンクするには  
  
1.  **\[ファイル\]** メニューの **\[新規作成\]** をポイントし、**\[プロジェクト\]** をクリックします。  
  
2.  **\[プロジェクトの種類\]** ペインで、**\[win32\]** をクリックします。  
  
3.  **\[テンプレート\]** ペインで、**\[Win32 コンソール アプリケーション\]** をクリックし、プロジェクトに名前を付けます。  
  
4.  C ソース コードを含むファイルをプロジェクトに追加します。  
  
5.  **\[ビルド\]** メニューの **\[ビルド\]** をクリックし、プロジェクトをビルドします。  
  
#### Bounce.c マルチスレッド プログラムをコマンド ラインからコンパイルおよびリンクするには  
  
1.  次のように、プログラムをコンパイルしてリンクします。  
  
    ```  
    CL BOUNCE.C  
    ```  
  
## 参照  
 [C と Win32 を使用するマルチスレッド](../parallel/multithreading-with-c-and-win32.md)