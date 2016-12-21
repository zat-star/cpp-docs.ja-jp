---
title: "例外処理 : 独自関数からの例外のスロー | Microsoft Docs"
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
  - "例外, スロー"
  - "関数 [C++], スロー (例外を)"
  - "スロー (例外を), 関数から"
ms.assetid: 492976e8-8804-4234-8e8f-30dffd0501be
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 例外処理 : 独自関数からの例外のスロー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC または他のライブラリ関数によってスローされる例外をキャッチするために MFC の例外処理のメリットをのみ使用することができます。  ライブラリ コードによってスローされた例外をキャッチすることに加えて、例外状況に遭遇する関数を作成する場合は、独自のコードが例外をスローすることができます。  
  
 例外がスローされると、現在の関数の直接実行が停止し、最も内側例外フレームの **catch** ブロックにジャンプします。  例外の機能、関数の正常終了のパスをバイパスします。  したがって、正常終了で削除されているメモリ ブロックを削除することを確認する必要があります。  
  
#### 例外をスローするには  
  
1.  `AfxThrowMemoryException`などの MFC のヘルパー関数の 1 種類を使用します。  これらの関数は、適切な型の割り当て済み例外オブジェクトをスローします。  
  
     次の例では、関数は、いずれかの割り当てが失敗した場合は 2 個のメモリ ブロックを割り当てると、例外をスローします:  
  
     [!code-cpp[NVC_MFCExceptions#17](../mfc/codesnippet/CPP/exceptions-throwing-exceptions-from-your-own-functions_1.cpp)]  
  
     最初の割り当てが失敗した場合、メモリ不足の例外をスローすることができます。  最初の割り当てが成功した場合は、2 1 番目に失敗すると、例外をスローする前に、最初の割り当てブロックを解放する必要があります。  割り当てが両方とも成功した場合は、関数が終了するときに進み、ブロックを解除できます。  
  
     または  
  
2.  懸案事項の状態を示すためにユーザー定義例外を使用します。  例外として、型、クラス全体の項目もスローすることができます。  
  
     次の例では、エラーが発生した波のデバイスでサウンドをしようとすると、例外をスローします。  
  
     [!code-cpp[NVC_MFCExceptions#18](../mfc/codesnippet/CPP/exceptions-throwing-exceptions-from-your-own-functions_2.cpp)]  
  
> [!NOTE]
>  MFC の例外の既定の処理は `CException` オブジェクト適用されます \(および `CException`オブジェクト\-派生クラスへのポインターにのみ\)。  上の例のバイパス MFC 例外の機能。  
  
## 参照  
 [例外処理](../mfc/exception-handling-in-mfc.md)