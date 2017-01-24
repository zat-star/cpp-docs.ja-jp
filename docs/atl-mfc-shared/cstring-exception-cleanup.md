---
title: "文字列 : CString の例外の後処理 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CString オブジェクト, 例外"
  - "例外処理, クリーンアップ コード"
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 文字列 : CString の例外の後処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC の以前のバージョンでは、使用後の [CString](../atl-mfc-shared/reference/cstringt-class.md) のオブジェクトをクリーンアップすることが重要です。  MFC バージョン 3.0 と低速で、明示的なクリーンアップによっては不要になります。  
  
 MFC は、利用する C\+\+ 例外処理機構の下に、例外の後にクリーンアップを気にする必要はありません。  ついては、「C\+\+ がスタックをどのように例外がキャッチされた後、[try、catch、throw ステートメント](../cpp/try-throw-and-catch-statements-cpp.md)アンワインド」を参照してください。  C\+\+ のキーワードと **trycatch**ではなく、MFC **TRY**\/**CATCH** のマクロを使用しても、MFC は、C\+\+ 例外機構を基に使用しているため、まだ明示的にクリーンアップする必要はありません。  
  
## 参照  
 [文字列](../atl-mfc-shared/strings-atl-mfc.md)   
 [例外処理](../mfc/exception-handling-in-mfc.md)