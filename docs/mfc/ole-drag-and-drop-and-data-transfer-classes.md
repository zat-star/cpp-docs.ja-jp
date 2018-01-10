---
title: "OLE ドラッグ アンド ドロップおよびデータ転送クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.ole
dev_langs: C++
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0e8c5a54184bcf6450bf39b39a6b90d7865c09d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>OLE ドラッグ アンド ドロップおよびデータ転送クラス
これらのクラスは、OLE データ転送に使用されます。 これらは、アプリケーションでクリップボードの使用方法やドラッグ アンド ドロップの間で転送されるデータを許可します。  
  
 [COleDropSource](../mfc/reference/coledropsource-class.md)  
 開始から終了までドラッグ アンド ドロップ操作を制御します。 このクラスは、ドラッグ操作の開始時と終了時に決定します。 カーソルからのフィードバックは、ドラッグ アンド ドロップ操作中にも表示されます。  
  
 [COleDataSource](../mfc/reference/coledatasource-class.md)  
 アプリケーション データをデータ転送を提供するときに使用されます。 `COleDataSource`オブジェクト指向クリップボード オブジェクトとして表示できませんでした。  
  
 [関数](../mfc/reference/coledroptarget-class.md)  
 ドラッグ アンド ドロップ操作の対象を表します。 A`COleDropTarget`オブジェクトは、画面上のウィンドウに対応しています。 これは、すべてのデータにドロップし、実際のドロップ操作を実装をそのまま使用するかどうかを判断します。  
  
 [COleDataObject](../mfc/reference/coledataobject-class.md)  
 受信者側として使用される`COleDataSource`です。 `COleDataObject`オブジェクトによって格納されるデータへのアクセスを提供する、`COleDataSource`オブジェクト。  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../mfc/class-library-overview.md)

