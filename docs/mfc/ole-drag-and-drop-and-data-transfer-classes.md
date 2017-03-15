---
title: "OLE ドラッグ アンド ドロップとデータ転送クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX クラス [C++]"
  - "データ転送 [C++], OLE"
  - "データ転送クラス [C++]"
  - "ドラッグ アンド ドロップ [C++], クラス"
  - "OLE のドラッグ アンド ドロップ [C++], およびデータ転送クラス"
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE ドラッグ アンド ドロップとデータ転送クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのクラスは、OLE データ転送に使用されます。  これらは、データがクリップボードを使用して、ドラッグ アンド ドロップを使用してアプリケーションの間を移動できます。  
  
 [COleDropSource](../mfc/reference/coledropsource-class.md)  
 ドラッグ アンド ドロップ操作の開始から終了まで制御します。  このクラスは、ドラッグ操作の起動時、いつ終了するかを指定します。  また、ドラッグ アンド ドロップ操作中のカーソルのフィードバックを表示します。  
  
 [COleDataSource](../mfc/reference/coledatasource-class.md)  
 アプリケーションがデータ転送にデータを提供するときに使用します。  `COleDataSource` は オブジェクト指向クリップボード オブジェクトと見なすことができます。  
  
 [COleDropTarget](../Topic/COleDropTarget%20Class.md)  
 ドラッグ アンド ドロップ操作のターゲットを表します。  `COleDropTarget` オブジェクトは画面のウィンドウに対応します。  かどうかにドロップされたデータを受け入れるようにし、実際のドロップ操作を実装します。  
  
 [指定した COleDataObject](../mfc/reference/coledataobject-class.md)  
 `COleDataSource`の受信側として使用されます。  `COleDataObject` オブジェクトは `COleDataSource` オブジェクトに格納されたデータへのアクセスを提供します。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)