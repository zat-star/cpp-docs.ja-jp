---
title: "シリアル化機構のバイパス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- archive objects [MFC]
- bypassing serialization
- archives [MFC], serialization
- serialization [MFC], bypassing
- archives [MFC]
- serialization [MFC], role of framework
- serialization [MFC], overriding
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 510e6ed244fb8920c55c4b3ffedcbd0801c3e202
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="bypassing-the-serialization-mechanism"></a>シリアル化機構のバイパス
きたように、フレームワークは、ファイルからデータを読み書きする既定の方法を提供します。 ほとんどのアプリケーションのニーズに適したアーカイブ オブジェクトをシリアル化します。 このようなアプリケーションは、ファイルを読み込み、メモリに完全に、によりユーザーは、ファイルを更新でき、し、再度ディスクに更新されたバージョンを書き込みます。  
  
 ただし、一部のアプリケーションがまったく違う方法でデータを操作し、これらのアプリケーションのアーカイブをシリアル化は適していません。 例としては、データベース プログラム、大きなファイルの一部だけを編集するプログラム、プログラム テキストのみのファイルの書き込みをデータ ファイルを共有するプログラムです。  
  
 このような場合は、オーバーライドすることができます、 [Serialize](../mfc/reference/cobject-class.md#serialize)関数を通じたファイル アクションを仲介する別の方法で、 [CFile](../mfc/reference/cfile-class.md)オブジェクトではなく、 [CArchive](../mfc/reference/carchive-class.md)オブジェクト。  
  
 使用することができます、**開く**、**読み取り**、**書き込み**、**閉じる**、および`Seek`クラスのメンバー関数`CFile`ファイルを開く、ファイル ポインターを移動その時点で (指定したバイト数) のレコードを読み取る (のシーク)、ファイル内の特定の時点まで、let、ユーザーの更新、レコードは、へレコードがバックアップ ファイルに書き込み、同じ時点でもう一度しシークします。 フレームワークは、ファイルを開くし、使用することができます、`GetFile`クラスのメンバー関数`CArchive`へのポインターを取得する、`CFile`オブジェクト。 オーバーライドすることができますもより高度で柔軟性の高い使用するため、[かまいません](../mfc/reference/cdocument-class.md#onopendocument)と[呼び出す必要はありません](../mfc/reference/cdocument-class.md#onsavedocument)クラスのメンバー関数`CWinApp`です。 詳細については、クラスを参照してください。 [CFile](../mfc/reference/cfile-class.md)で、 *『 MFC リファレンス*です。  
  
 このシナリオでは、`Serialize`をしない場合は、たとえば、ドキュメントを閉じるときに最新に保持するファイルのヘッダーの読み書きがある、何もオーバーライドしません。  
  
## <a name="see-also"></a>参照  
 [ドキュメントの使い方](../mfc/using-documents.md)

