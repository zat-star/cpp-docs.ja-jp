---
title: "ファイルの読み書き | Microsoft Docs"
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
  - "CFile クラス, オブジェクト"
  - "CFile クラス, 読み取りと書き込み (CFile オブジェクトを)"
  - "例 [MFC], 読み取り (ファイルを)"
  - "例 [MFC], 書き込み (ファイルへの)"
  - "ファイル [C++], 読み取り"
  - "ファイル [C++], 書き込み"
  - "MFC [C++], ファイルの操作"
  - "読み取り (ファイルを)"
  - "書き込み (ファイルへの) [C++]"
ms.assetid: cac0c826-ba56-495f-99b3-ce6336f65763
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ファイルの読み書き
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C ランタイム ライブラリのファイル処理関数を使用した場合は、MFC の読み取りと書き込み操作が使い慣れているようです。  ここでは、直接から読み取り、`CFile` オブジェクトに直接書き込むことについて説明します。  また [CArchive](../mfc/reference/carchive-class.md) クラスで、バッファリングされたファイル I\/O を行うことができます。  
  
#### から読み取り、ファイルに書き込むには  
  
1.  ファイルに対するデータの読み書きに **読み取り** と **Write** メンバー関数を使用します。  
  
     または  
  
2.  `Seek` のメンバー関数は、ファイル内のオフセット仕様に移動する場合にも使用できます。  
  
 **読み取り** は バッファーの読み取りにポインターとバイト数を受け取り、Read 実際のバイト数を返します。  ファイルの終端の \(EOF\) に達したためにバイトに必要な文字数を読み込むことができない場合は、実際に読み取られたバイト数が返されます。  どの読み取りエラーが発生すると、例外がスローされます。  **Write** は **読み取り**に似ていますが、書き込んだバイト数が返されます。  書き込みでエラーが発生した場合、指定されたすべてのバイトを書き込みが含まれている例外がスローされます。  `CFile` の有効なオブジェクトがある場合は、それを読み取るか、そのファイルに次の例のように記述できます:  
  
 [!code-cpp[NVC_MFCFiles#2](../mfc/codesnippet/CPP/reading-and-writing-files_1.cpp)]  
  
> [!NOTE]
>  通常 **try**\/**catch** の例外処理ブロック内の入出力操作を実行する必要があります。  詳細については、「[Exception Handling \(MFC\)](../mfc/exception-handling-in-mfc.md)」を参照してください。  
  
## 参照  
 [ファイル](../mfc/files-in-mfc.md)