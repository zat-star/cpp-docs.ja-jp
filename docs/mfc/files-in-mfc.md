---
title: "MFC のファイル | Microsoft Docs"
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
  - "バイナリ アクセス"
  - "バイナリ アクセス, バイナリ ファイルの操作 (MFC の)"
  - "ファイル I/O クラス [C++]"
  - "ファイル [C++], 操作"
  - "ファイル [C++], MFC"
  - "ファイル [C++], シリアル化"
  - "I/O [C++], MFC クラス"
  - "I/O [MFC]"
  - "MFC [C++], ファイルの操作"
  - "永続化 [C++]"
  - "シリアル化 [C++], MFC ファイル"
ms.assetid: ae25e2c5-2859-4679-ab97-438824e93ce1
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC のファイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC \(Microsoft Foundation Class\) ライブラリでは、通常の入出力操作を [CFile](../mfc/reference/cfile-class.md) クラスで処理します。  ここでは、ファイルを開く方法と閉じる方法、およびファイルに対する読み書きを行う方法について説明します。  また、ファイルの状態の操作方法についても説明します。  オブジェクト ベースの MFC のシリアル化機能でもファイルの読み書きを行うことができます。シリアル化機能の使い方については、「[シリアル化](../Topic/Serialization%20in%20MFC.md)」を参照してください。  
  
> [!NOTE]
>  MFC の **CDocument** クラスのオブジェクトを使うと、シリアル化操作の大部分をフレームワークに任せることができます。  フレームワークは、`CFile` クラスのオブジェクトを自動的に作成し、使います。  したがって、**CDocument** クラスのメンバー関数 `Serialize` をオーバライドするコードを書くだけで済みます。  
  
 `CFile` クラスは、バイナリ ファイルに対する汎用的な操作のインターフェイスを提供します。  `CFile` の派生クラスである `CStdioFile` クラスと `CMemFile` クラスおよび `CMemFile` の派生クラスである `CSharedFile` クラスは、より特殊なファイル処理機能を提供します。  
  
 代替方法の詳細については、「ランタイム ライブラリ リファレンス」の「[ファイル処理](../c-runtime-library/file-handling.md)」を参照してください。  
  
 `CFile` の派生クラスについては、「[階層図](../mfc/hierarchy-chart.md)」を参照してください。  
  
## 目的に合ったトピックをクリックしてください  
 *CFile を使う*  
  
-   [ファイルを開く](../Topic/Opening%20Files.md)  
  
-   [ファイルの読み書き](../mfc/reading-and-writing-files.md)  
  
-   [ファイルを閉じる](../mfc/closing-files.md)  
  
-   [ファイルの状態の操作](../mfc/accessing-file-status.md)  
  
 *MFC のシリアル化を使う \(オブジェクトの保存\)*  
  
-   [シリアル化 : シリアル化可能なクラスの作成](../mfc/serialization-making-a-serializable-class.md)  
  
-   [シリアル化 : オブジェクトのシリアル化](../Topic/Serialization:%20Serializing%20an%20Object.md)  
  
-   [CArchive オブジェクトを作成する 2 つの方法](../mfc/two-ways-to-create-a-carchive-object.md)  
  
-   [CArchive \<\< と \>\> 演算子を使用します。](../mfc/using-the-carchive-output-and-input-operators.md)  
  
-   [アーカイブを通じた CObject の格納と読み込み](../Topic/Storing%20and%20Loading%20CObjects%20via%20an%20Archive.md)  
  
## 参照  
 [概念](../mfc/mfc-concepts.md)   
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)   
 [CArchive クラス](../mfc/reference/carchive-class.md)   
 [CObject クラス](../Topic/CObject%20Class.md)   
 [How Do I: Use the CFile Class? \(操作方法: CFile クラスを使用する\)](http://go.microsoft.com/fwlink/?LinkId=128046)