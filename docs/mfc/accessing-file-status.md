---
title: "ファイルの状態 |Microsoft ドキュメント"
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
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ff93028c192a735ec75721d3dfdb9929a35edad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="accessing-file-status"></a>ファイルの状態の操作
`CFile`サポートしているファイルの状態のファイルが存在するかどうかなど、作成と変更の日付と時間、論理サイズ、およびパスを取得します。  
  
### <a name="to-get-file-status"></a>ファイルの状態を取得するには  
  
1.  使用して、 [CFile](../mfc/reference/cfile-class.md)クラスを取得し、ファイルに関する情報を設定します。 1 つの便利なアプリケーションは、使用する、`CFile`静的メンバー関数**GetStatus**ファイルが存在するかどうかを確認します。 **GetStatus**指定したファイルが存在しない場合は 0 を返します。  
  
 結果を使用するため、 **GetStatus**を使用するかどうかを決定する、 **CFile::modeCreate**次の例に示すように、ファイルを開くときにフラグを設定します。  
  
 [!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]  
  
 関連情報については、次を参照してください。[シリアル化](../mfc/serialization-in-mfc.md)です。  
  
## <a name="see-also"></a>参照  
 [ファイル](../mfc/files-in-mfc.md)

