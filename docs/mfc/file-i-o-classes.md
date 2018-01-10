---
title: "ファイルは-o クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.file
dev_langs: C++
helpviewer_keywords:
- disk file classes [MFC]
- stdio classes [MFC]
- OLE streams [MFC]
- I/O [MFC], MFC classes
- translated stream classes [MFC]
- file I/O classes [MFC]
- I/O [MFC], classes
- sockets classes [MFC]
- stream classes [MFC]
- memory file classes [MFC]
ms.assetid: 92821c3f-d9e1-47f6-98c9-3b632d86e811
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 454e64d67321282030126d2aab023e9f587c1cca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="file-io-classes"></a>ファイル I/O クラス
これらのクラスは、従来のディスク ファイル、メモリ内のファイル、Active ストリーム、および Windows ソケットへのインターフェイスを提供します。 派生したすべてのクラス`CFile`で使用できる、`CArchive`オブジェクトをシリアル化を実行します。  
  
 特に、次のクラスを使用して`CArchive`と`CFile`入力/出力処理を記述する場合は、します。 通常これらのクラスから派生する必要はありません。 アプリケーション フレームワークの既定の実装を使用する場合、**開く**と**保存**コマンドを使って、**ファイル**メニューは、ファイル I/O を処理する (クラスを使用して`CArchive`) ドキュメントをオーバーライドする場合に限り、`Serialize`を指定する関数は、ドキュメントがその内容をシリアル化する方法に関する詳細情報します。 ファイルのクラスとシリアル化する方法の詳細については、記事を参照してください。 [MFC のファイル](../mfc/files-in-mfc.md)」および「[シリアル化](../mfc/serialization-in-mfc.md)です。  
  
 [CFile](../mfc/reference/cfile-class.md)  
 バイナリ ディスク ファイルへのファイル インターフェイスを提供します。  
  
 [CStdioFile](../mfc/reference/cstdiofile-class.md)  
 提供、`CFile`テキスト モードで通常のバッファー済みストリーム ディスク ファイルへのインターフェイスです。  
  
 [CMemFile](../mfc/reference/cmemfile-class.md)  
 提供、`CFile`のインメモリ ファイルへのインターフェイスです。  
  
 [多くの場合](../mfc/reference/csharedfile-class.md)  
 提供、`CFile`共有メモリ内のファイルへのインターフェイスです。  
  
 [関数](../mfc/reference/colestreamfile-class.md)  
 COM を使用して`IStream`インターフェイスを提供する`CFile`複合ファイルへのアクセス。  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md)  
 提供、 `CFile` Windows ソケットへのインターフェイスです。  
  
## <a name="related-classes"></a>関連するクラス  
 [CArchive](../mfc/reference/carchive-class.md)  
 連携して、`CFile`シリアル化を使用したオブジェクトの永続的なストレージを実装するオブジェクト (を参照してください[cobject::serialize](../mfc/reference/cobject-class.md#serialize))。  
  
 [CArchiveException](../mfc/reference/carchiveexception-class.md)  
 アーカイブの例外。  
  
 [CFileException](../mfc/reference/cfileexception-class.md)  
 ファイル指向の例外。  
  
 [CFileDialog](../mfc/reference/cfiledialog-class.md)  
 開く、またはファイルを保存するためには、標準のダイアログ ボックスを提供します。  
  
 [関数](../mfc/reference/crecentfilelist-class.md)  
 最近使用した (MRU) ファイルの一覧を保持します。  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../mfc/class-library-overview.md)

