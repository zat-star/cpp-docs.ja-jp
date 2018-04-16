---
title: "シリアル化: オブジェクトのシリアル化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37e688a3619cd203e61997999a9b7eb7651d73fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="serialization-serializing-an-object"></a>シリアル化 : オブジェクトのシリアル化
アーティクル[シリアル化: シリアル化可能なクラスの作成](../mfc/serialization-making-a-serializable-class.md)クラスをシリアル化可能にする方法を示しています。 シリアル化可能なクラスを作成したら、そのクラス経由でのファイルとの間のオブジェクトをシリアル化することができます、 [CArchive](../mfc/reference/carchive-class.md)オブジェクト。 この記事の内容について説明します。  
  
-   [CArchive オブジェクトがどのような](../mfc/what-is-a-carchive-object.md)します。  
  
-   [CArchive を作成する方法は 2](../mfc/two-ways-to-create-a-carchive-object.md)です。  
  
-   [CArchive を使用する方法 <\<と >> 演算子](../mfc/using-the-carchive-output-and-input-operators.md)です。  
  
-   [格納とアーカイブを通じた Cobject を読み込み](../mfc/storing-and-loading-cobjects-via-an-archive.md)です。  
  
 Framework ドキュメントをシリアル化、アーカイブを作成するか明示的に作成することができます、`CArchive`自分でオブジェクトします。 使用して、ファイルと、シリアル化可能なオブジェクトの間でデータを転送することができます、<\<と >> 演算子`CArchive`または場合によっては、呼び出すことによって、`Serialize`の関数、 `CObject`-クラスを派生します。  
  
## <a name="see-also"></a>参照  
 [シリアル化](../mfc/serialization-in-mfc.md)

