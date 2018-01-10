---
title: "コンパイルとマルチ スレッド プログラムのリンク |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- compiling multithreaded programs
- multithreading [C++], linking programs
- threading [C++], linking programs
- multithreading [C++], compiled programs
- threading [C++], compiled programs
- compiling source code [C++], multithread programs
- linking [C++], multithread programs
ms.assetid: 27589afc-daf2-4f26-b868-a99de5c9dfec
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0145c480d74cb1978c1b6caef65489eae96501c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiling-and-linking-multithread-programs"></a>マルチスレッド プログラムのコンパイルとリンク
Bounce.c プログラムがで導入された[マルチ スレッドの C サンプル プログラム](../parallel/sample-multithread-c-program.md)です。  
  
 プログラムはコンパイルが既定ではマルチ スレッドです。  
  
#### <a name="to-compile-and-link-the-multithread-program-bouncec-from-within-the-development-environment"></a>コンパイルおよびリンク Bounce.c 開発環境内でマルチ スレッド プログラム  
  
1.  **[ファイル]** メニューの **[新規作成]**をポイントし、 **[プロジェクト]**をクリックします。  
  
2.  **プロジェクトの種類** ウィンドウで、をクリックして**Win32**です。  
  
3.  **テンプレート** ウィンドウで、をクリックして**Win32 コンソール アプリケーション**、プロジェクト名とします。  
  
4.  プロジェクトに C ソース コードを含むファイルを追加します。  
  
5.  **ビルド** メニューのをクリックして、プロジェクトをビルド、**ビルド**コマンド。  
  
#### <a name="to-compile-and-link-the-multithread-program-bouncec-from-the-command-line"></a>コマンドラインからのマルチ スレッド プログラム Bounce.c コンパイルおよびリンクするには  
  
1.  コンパイルし、プログラムをリンクします。  
  
    ```  
    CL BOUNCE.C  
    ```  
  
## <a name="see-also"></a>参照  
 [C と Win32 を使用するマルチスレッド](../parallel/multithreading-with-c-and-win32.md)