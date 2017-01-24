---
title: "データ オブジェクトとデータ ソース (OLE) | Microsoft Docs"
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
  - "データ オブジェクト [C++], 定義"
  - "データ ソース [C++], 定義"
  - "データ転送 [C++]"
  - "データ転送 [C++], 定義"
  - "OLE [C++], データ オブジェクト"
  - "OLE [C++], データ ソース"
  - "OLE [C++], データ転送"
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# データ オブジェクトとデータ ソース (OLE)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クリップボードを使用するか、ドラッグ アンド ドロップによるデータ転送を実行すると、データをソースとターゲットがあります。  1 種類のアプリケーションでコピーにデータを提供し、別のアプリケーションが Word などのコントロールを使用できます。  転送の同じデータのさまざまな操作が正常に完了するために実行する転送に必要な各端。  Microsoft Foundation Class \(MFC\) ライブラリはこの転送の両側を表すクラスを 2 つあります。:  
  
-   \(`COleDataSource` オブジェクトによって実装される\) データ ソースは、データ転送のソース側を表します。  これらはソース アプリケーションでデータをクリップボードにコピーするか、またはデータがドラッグ アンド ドロップ操作によって提供されるときに作成されます。  
  
-   \(`COleDataObject` オブジェクトによって実装される\) データ オブジェクトは、データの転送先の辺を表します。  これらは先のアプリケーションにドロップするデータがある場合、クリップボードからの貼り付け操作を実行することを要求するときに作成されます。  
  
 次のトピックでは、アプリケーションでデータ オブジェクトとデータ ソースの使用方法について説明します。  この情報は、コンテナーとサーバーの両方にアプリケーション データをコピーして貼り付けるための両方になる場合があるため、適用されます。  
  
-   [データ オブジェクトとデータ ソース: 作成および破棄](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [データ オブジェクトとデータ ソース: 操作](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## このセクションの内容  
 [ドラッグ アンド ドロップ](../mfc/drag-and-drop-ole.md)  
  
 [クリップボード](../mfc/clipboard.md)  
  
## 参照  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleDataObject クラス](../mfc/reference/coledataobject-class.md)   
 [COleDataSource クラス](../mfc/reference/coledatasource-class.md)