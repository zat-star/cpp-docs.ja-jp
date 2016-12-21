---
title: "読み込み時にクライアント アプリケーションのパフォーマンスを向上するための最適化手法 | Microsoft Docs"
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
  - "DLL [C++], 最適化"
  - "最適化 [C++], DLL"
  - "パフォーマンス [C++], DLL"
ms.assetid: 2f8bbfb5-08b9-4a35-8302-25a1966881b1
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 読み込み時にクライアント アプリケーションのパフォーマンスを向上するための最適化手法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC に静的にリンクするレギュラー DLL を動的にリンクするレギュラー DLL に変更すると、ファイルを小型化できます。  
  
 DLL にエクスポート関数が多数ある場合は、**\_\_declspec\(dllexport\)** ではなく .def ファイルを使用して関数をエクスポートします。エクスポートする関数ごとに [NONAME 属性](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)を指定します。  DLL のエクスポート テーブルに序数値だけが入り、関数名が格納されないので、ファイル サイズが小さくなります。  
  
 アプリケーションを読み込むと、暗黙にリンクされている DLL も一緒に読み込まれます。  読み込み時のパフォーマンスを向上するには、この DLL を複数に分割します。  呼び出し側アプリケーションが読み込み直後に使用する関数だけを 1 つの DLL にまとめ、アプリケーションに暗黙にリンクします。  呼び出し側アプリケーションですぐには必要でないその他の関数は、別の DLL に読み込み、アプリケーションをその DLL に明示的にリンクします。  詳細については、「[リンク方式の使い分け](../build/determining-which-linking-method-to-use.md)」を参照してください。  
  
## 参照  
 [DLL に関してよく寄せられる質問](../build/dll-frequently-asked-questions.md)