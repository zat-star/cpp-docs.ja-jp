---
title: "シリアル化機構のバイパス | Microsoft Docs"
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
  - "アーカイブ オブジェクト [C++]"
  - "アーカイブ [C++]"
  - "アーカイブ [C++], シリアル化"
  - "シリアル化のバイパス"
  - "シリアル化 [C++], バイパス"
  - "シリアル化 [C++], オーバーライド"
  - "シリアル化 [C++], 役割 (フレームワークの)"
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# シリアル化機構のバイパス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

参照したので、フレームワークはファイルに対するデータの読み書きに使用する既定の方法を提供します。  アーカイブ オブジェクトにシリアル化は偉大なユーザーのニーズに多くのアプリケーションに適しています。  このようなアプリケーションは、ファイル全体を読み込み、ユーザーがファイルを更新するようにし、ディスクに更新バージョンを再度書き込みます。  
  
 ただし、アプリケーションによっては、データが大幅に異なる方法で機能し、これらのアプリケーションに対してアーカイブによるシリアル化が適しているとは言えません。  たとえば、データベース プログラム、テキストのみファイルを書き込み、およびプログラムで編集する大きなファイルの一部のみ、データ ファイルを共有するプログラムが含まれます。  
  
 このような場合、[CArchive](../mfc/reference/carchive-class.md) オブジェクトではなく、[CFile](../mfc/reference/cfile-class.md) オブジェクトを使用してファイルの動作を仲介するに [シリアル化する](../Topic/CObject::Serialize.md) 関数を別の方法でオーバーライドできます。  
  
 **開く**、**読み取り**、**Write**、**閉じる**を使用して、ファイルを開く `CFile` クラスの `Seek` のメンバー関数は、ファイル ポインター \(シーク\) をファイル内の特定の位置に移動するには、選択したレコード \(バイト数\) を読み込んでいる場合、ユーザーがレコードを更新するようにし、同じポイントに再度検索し、ファイルまでレコードを書き込みます。  フレームワークによってファイルを開き、`CFile` オブジェクトへのポインターを取得するに `CArchive``GetFile` クラスのメンバー関数を使用できます。  さらに高度なと柔軟性を持った使用のために、クラス `CWinApp`の [OnOpenDocument](../Topic/CDocument::OnOpenDocument.md) と [OnSaveDocument](../Topic/CDocument::OnSaveDocument.md) のメンバー関数をオーバーライドします。  詳細については、" *MFC リファレンス"の*" [CFile](../mfc/reference/cfile-class.md) クラスを参照します。  
  
 このシナリオでは、`Serialize` のオーバーライドは Nothing、しません。たとえば、このファイルをドキュメントを閉じる最新の状態に維持するにヘッダー ファイルの読み取りと書き込みを選択する必要があります。  
  
## 参照  
 [ドキュメントの使い方](../mfc/using-documents.md)