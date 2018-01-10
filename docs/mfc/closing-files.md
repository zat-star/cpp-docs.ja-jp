---
title: "ファイルを閉じる |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27b1c59c952b022c7382db7d6b2dcb660cca2e9a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="closing-files"></a>ファイルを閉じる
通常どおり I/O 操作で、ファイルを終了すると、閉じてください。  
  
#### <a name="to-close-a-file"></a>ファイルを閉じる  
  
1.  使用して、**閉じる**メンバー関数。 この関数は、ファイル システム ファイルを閉じ、必要な場合は、バッファーをフラッシュします。  
  
 割り当てた場合、 [CFile](../mfc/reference/cfile-class.md)フレーム上のオブジェクト (に示す例のように[ファイルを開く](../mfc/opening-files.md))、オブジェクトが自動的に終了して、スコープ外になったときに破棄されるあります。 削除することに注意してください、`CFile`オブジェクトには、ファイル システムで物理ファイルは削除されません。  
  
## <a name="see-also"></a>参照  
 [ファイル](../mfc/files-in-mfc.md)

